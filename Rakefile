require 'rake/clean'
require 'rexml/document'

LAYOUT_SRC = FileList.new('_includes/*.haml','_layouts/*.haml', 'index.haml')
LAYOUT_HTML = LAYOUT_SRC.ext('html')
SCSS = FileList.new('css/*.scss')
CSS = SCSS.ext('css')
LAYOUT = LAYOUT_HTML + CSS
POSTS = FileList.new('_posts/*.md')

CLOBBER.include('_site')
CLEAN.include('tags/*.*')
CLEAN.include(LAYOUT)
CLEAN.include('css/combined.css')

rule '.html' => ['.haml'] do |t|
    sh %{ haml -E utf-8 #{t.source} #{t.name.sub(/_haml\./,'.')} }
end

rule '.css' => ['.scss'] do |t|
    sh %{ sass -t compressed #{t.source} #{t.name} }
end

def aggregate_keywords(category,posts)
  keywords = SortedSet.new()
  keywords << category
  posts.each do |post|
    post_data = post.to_liquid
    if post_data.has_key? 'keywords' 
      post_data['keywords'].each do |word|
        keywords << word
      end
    end
  end
  return keywords.to_a.join(',')
end

def concatenate_files(output_filename, input_files)
  File.open(output_filename, "a+") do |out|
    out.puts input_files.map{ |s| IO.read(s)}
  end
end

def create_loc(path)
  name = File.basename(path, '.md') 
  name[10] ='/'
  loc = REXML::Element.new "loc" 
  loc.text = "http://basbossink.github.com/" + name + "/"
  
  loc
end

def create_lastmod(path)
  require 'time'
  lastmod = REXML::Element.new "lastmod"
  date = File.mtime(path)
  lastmod.text = date.iso8601
  lastmod
end

def create_url(path,date)
  url = REXML::Element.new "url"
  url.add_element(create_loc(path))
  url.add_element(create_lastmod(path))
  url
end


def generate_sitemap()
  require 'find'
  sitemap = REXML::Document.new << REXML::XMLDecl.new("1.0", "UTF-8")
  urlset = REXML::Element.new "urlset"
  urlset.add_attribute("xmlns", 
        "http://www.sitemaps.org/schemas/sitemap/0.9")
  
  Find.find('_posts') do |path|
    unless FileTest.directory?(path) 
      puts "adding #{path} to sitemap"
      date = File.mtime(path)
      urlset.add_element(create_url(path,date))
    end
  end
  sitemap.add_element(urlset)
  sitemap
end

def write_sitemap(sitemap)
  file = File.new("sitemap.xml", "w")
  formatter = REXML::Formatters::Default::new(true)
  formatter.write(sitemap, file)
  file.close
end

def validate_sitemap()
  require 'Nokogiri'
  xsd = Nokogiri::XML::Schema(File.read("sitemap.xsd"))
  doc = Nokogiri::XML(File.read("sitemap.xml"))

  xsd.validate(doc).each do |error|
    puts error.message
  end
end

namespace :sitemap do
  task :generate do
    write_sitemap(generate_sitemap())
  end

  task :validate => :generate do 
    validate_sitemap()
  end
end

namespace :tags do

  task :clean do 
    rm_rf "tags"
    mkdir "tags"
  end

  task :generate do
    puts 'Generating tags...'
    require 'rubygems'
    require 'jekyll'
    include Jekyll::Filters

    options = Jekyll.configuration({})
    site = Jekyll::Site.new(options)
    site.read_posts('')
    site.categories.sort.each do |category, posts|
      keywords = aggregate_keywords(category, posts)
      html= <<-HTML
---
layout: default
title: Posts tagged #{category}
keywords: [#{keywords}]
---
HTML
      posts.each do |post|
        post_data = post.to_liquid
        html << <<-HTML
<h2><a href="#{post_data['url']}">#{post_data['title']}</a></h2>
{% assign my_date = ' #{post_data['date'].strftime("%a %d %b %Y")}' %}
#{post_data['content']}
#{'<hr/>' unless post == posts.last}
HTML
      end
      File.open("tags/#{category.gsub(/\s+/,'-')}.md", 'w+') do |file|
        file.puts html
      end
    end
  end
end

desc 'Generate html and css from sources'
task :build => LAYOUT do
end

desc 'commpress html'
task :shrink => :build do
  rm_rf 'css/combined.css'
  concatenate_files("css/combined.css",FileList['css/*.css'])
  sh %{ java -jar C:/Users/bas/programs/yuicompressor-2.4.6/build/yuicompressor-2.4.6.jar css/combined.css -o css/combined.css }
end

desc 'Build and start server'
task :server => :default do
  sh %{ jekyll --server }
end

desc 'Count words and lines of post'
task :count => POSTS do 
  POSTS.each do | post | 
    output = IO.popen( "pandoc -t plain #{post}") 
    lc = wc = 0
    output.each_line do |line| 
      lc += 1
      wc += line.split.size
    end
    puts "#{post.pathmap("%f")} has #{lc} lines and #{wc} words"
  end
end

desc "Create per tag pages and rest"
task :default => [
                  :shrink, 
                  "tags:generate",
                  "sitemap:generate"
                 ]











