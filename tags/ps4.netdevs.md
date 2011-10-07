---
layout: default
title: Posts tagged ps4.netdevs
keywords: [.NET,.NET development,PowerShell,PowerShell advocacy,development,ps4.netdevs]
---
<h2><a href="/2011-06-19/ps4.netdevs-0-what-and-why/">PS for .NET devs part 0: PowerShell what is it and why should I care?</a></h2>
{% assign my_date = ' Sun 19 Jun 2011' %}
Being a big [PowerShell][1] fan but not seeing many fellow developers around me use it, I
thought [PowerShell][1] could use some promotion among .NET
developers. This inspired me to start a series of blog
posts showing the great stuff [PowerShell][1] has to offer .NET
developers. The outline I have defined up to now looks like this:

1. Getting started with [PowerShell][1] 
1. [PowerShell][1]] as a better shell
1. The syntax of the [PowerShell][1] language
1. Listing the Targets in your MSBuild file
1. Getting an overview of your code-base
1. Shutting down the pesky virus scanner with WMI events
1. Looking into your MongoDB data with [PowerShell][1]
1. Freeing yourself from xml build languages with psake
1. Testing your .NET code using Pester
1. Automated UI testing with [PowerShell][1]
1. Writing a Visual Studio extension in 1 line of [PowerShell][1]
1. Using [PowerShell][1] to add Twitter and Jabber to VS
1. Using chewie and nuget to automate adding and updating libraries
1. Lightweight code generation with here string interpolation
1. Rapid UI prototyping with Show-UI
1. Automating debugging with WinDbg
1. Basic monitoring with [PowerShell][1]
1. Graphing monitoring data with [PowerShell][1] and gnuplot
1. Automating deployments
1. Automate smoke tests using [PowerShell][1] and VirtualBox
1. Using [PowerShell][1] to configure your application
1. Using [PowerShell][1] as an extensibillity point

This should give you a sense of the breadth and depth that is
available to you when you harness the power of [PowerShell][1].

## What is [PowerShell][1]? 
Citing [Wikipedia on Windows Powershell][2]:

>Windows PowerShell is Microsoft's task automation framework,
>consisting of a command-line shell and associated scripting language
>built on top of, and integrated with the .NET Framework. PowerShell
>provides full access to COM and WMI, enabling administrators to
>perform administrative tasks on both local and remote Windows systems.  

To expand on that a little [PowerShell][1] is built on .NET and uses
the .NET object model to give it it's competitive advantage.
Tasks ([Cmdlets][7] as they are officially called) can be composed
using the pipeline. Think of a UNIX shell but instead
of text flowing through the pipelines, .NET objects flow
through the pipelines. This relieves the user from "prayer based
parsing" with tools like e.g. `cut`, `sed`, `awk`. Combine this with the reflection
capabilities .NET has to offer, automatic (type) conversions, 
advanced parameter binding and you have a discoverable,
composition friendly working environment. Quoting [Jeffrey Snover][8],
(the architect behind the product now responsible for the entire
windows server platform): "It's like programming with hand grenades."
Watch [this][9] great [Going Deep][10] [episode][9] and see how
[Jeffrey][8] talks about this in detail with [Erik Meijer][11].

## Why should I care about PowerShell?
When I tried searching for the answer to this question I came up with
a list of blog-posts that were all oriented toward the IT-pro. For
reference I've included the links below in the [References section](#references). 
Apart from the hints given in the outline above on why you should
care. You may find yourself writing a [PowerShell module][5],
[Provider][6] or [Cmdlet][7] to help your users interact with the
application you are writing sooner than you think. When that's the
case it is crucial you have experience in [PowerShell][1], especially
since [PowerShell][1] requires you to abide to some specific naming
conventions. Furthermore [PowerShell][1] users expect certain
behaviors from the functionality you provide to be the same as they
are accustomed to from using other [Cmdlets][7] and [Providers][6].

The list of [PowerShell][1] features that are most useful for a .NET
developer as far as I can come up with from the top of my head:

- [PowerShell][1] is a better shell
- [PowerShell][1] has very good support for working with xml
- [PowerShell][1] is easy to learn
- [Powershell][1] is an automation engine and a shell using a nice language
- [PowerShell][1] can be used to quickly lookup methods and/or experiment
with .NET types
- [PowerShell][1] easily talks to COM
- [PowerShell][1] can be used to query WMI, hookup to WMI events
- [PowerShell][1] has a built-in registry provider, which means
you can access the registry with the familiar `dir`, `copy` and `del`
commands
- for those doing web development, the IIS team provides a [PowerShell][1]
module that covers 99% of IIS's functionality
- SQL Server 2008 and up have a very comprehensive [PowerShell][1]
module that contains both a [Provider][6] and a set of [Cmdlets][7].

I hope all of the above gets you intrigued and/or inspired to look into
[PowerShell][1], or at least to check back here for part 1 of
[this series][12]. Until next time, wield your new found powers wisely.

{% include date.inc %}
 
<h5 id="references">References</h5>
<div class="references">
<ul>
<li><a href='http://www.computerperformance.co.uk/powershell/#Reasons_to_Learn_Monad_' title='Reasons to learn Monad'>Richard Siddaway&#8217;s Blog: Reaons to learn Monad</a></li>
<li><a href='http://www.techrepublic.com/blog/10things/10-reasons-why-you-should-learn-to-use-powershell/1073' title='10 reasons why you should learn to use PowerShell'>TechRepublic: 10 reasons why you should learn to use PowerShell</a></li>
<li><a href='http://technet.microsoft.com/en-us/scriptcenter/dd742419' title='Scripting with Windows PowerShell'>Technet: Scripting with Windows PowerShell</a></li>
<li><a href='http://en.wikipedia.org/wiki/Windows_PowerShell' title='Wikipedia entry for Windows PowerShell'>Wikipedia: Windows PowerShell</a></li>
<li><a href='http://msdn.microsoft.com/en-us/library/ms714395(v=VS.85).aspx' title='Cmdlet Overview'>Cmdlet Overview</a></li>
<li><a href='http://msdn.microsoft.com/en-us/library/ee126186(v=vs.85).aspx' title='Windows PowerShell Provider Overview'>Windows Powerhell Provider Overview</a></li>
<li><a href='http://go.microsoft.com/fwlink/?LinkId=144916'
title='Writing a Windows PowerShell Module'>Writing a Windows
PowerShell Module</a></li>
<li><a
href='http://www.microsoft.com/presspass/exec/de/snover/default.mspx'
title='Jeffrey Snover'>Jeffrey Snover</a></li>
<li><a
href='http://channel9.msdn.com/shows/Going+Deep/Expert-to-Expert-Erik-Meijer-and-Jeffrey-Snover-Inside-PowerShell/'
title='Expert to Expert: Erik Meijer and Jeffrey Snover - Inside PowerShell'>Expert to Expert: Erik Meijer and Jeffrey Snover - Inside PowerShell</a></li>
<li><a href='http://channel9.msdn.com/Shows/Going+Deep' title='Going Deep'>Going Deep</a></li>
<li><a href='http://research.microsoft.com/en-us/um/people/emeijer/'
title='Erik Meijer'>Erik Meijer</a></li>
<li><a href='/tags/ps4.netdevs.html' title='PS for .NET devs category'>PS for .NET devs category</a></li>
</ul>
</div>

[1]: http://technet.microsoft.com/en-us/scriptcenter/dd742419 "Scripting with Windows PowerShell"
[2]: http://en.wikipedia.org/wiki/Windows_PowerShell "Wikipedia entry for Windows PowerShell"
[3]: http://www.computerperformance.co.uk/powershell/#Reasons_to_Learn_Monad_ "Reasons to learn Monad"
[4]: http://www.techrepublic.com/blog/10things/10-reasons-why-you-should-learn-to-use-powershell/1073 "10 reasons why you should learn to use PowerShell"
[5]: http://go.microsoft.com/fwlink/?LinkId=144916  "Writing a Windows PowerShell Module"
[6]: http://msdn.microsoft.com/en-us/library/ee126186(v=vs.85).aspx "Windows PowerShell Provider Overview"
[7]: http://msdn.microsoft.com/en-us/library/ms714395(v=VS.85).aspx "Cmdlet Overview"
[8]: http://www.microsoft.com/presspass/exec/de/snover/default.mspx "Jeffrey Snover"
[9]: http://channel9.msdn.com/shows/Going+Deep/Expert-to-Expert-Erik-Meijer-and-Jeffrey-Snover-Inside-PowerShell/ "Expert to Expert: Erik Meijer and Jeffrey Snover - Inside PowerShell"
[10]: http://channel9.msdn.com/Shows/Going+Deep "Going Deep" 
[11]: http://research.microsoft.com/en-us/um/people/emeijer/ "Erik Meijer"
[12]: /tags/ps4.netdevs.html "PS for .NET devs category"

<hr/>
<h2><a href="/2011-06-22/ps4.netdev-1-getting-started-with-powershell/">PS for .NET devs part 1: Getting started with PowerShell</a></h2>
{% assign my_date = ' Wed 22 Jun 2011' %}
After getting everybody warmed to the idea of learning [PowerShell][1]
in [part 0][0] of this [series][12]. Let's dig into a couple of ways
to get started with [PowerShell][1].

## The resource list
By now [PowerShell][1] has gained so much traction at this moment that
I could probably fill several dozen pages with links, pointers to the
excellent resources available on-line or in print. However I will
refrain myself to a couple starting points.

### On-line resources
- [PowerShell Community Toolbar][2]
  This is a browser plug-in that aggregates a big set of resources,
  from download links to the various [PowerShell][1] releases to a
  huge list of blogs filled with [PowerShell][1] content, to the
  localized [PowerShell][1] on-line help. Even if you are not very
  fond of browser toolbars I suggest you install it, take some time to
  follow the various links save them and uninstall the toolbar.
- [ScriptCenter PowerShell homepage][1] this contains loads of
  resources to get you started and should be considered the canonical
  starting point for finding [PowerShell][1] related resources. 
- [Windows PowerShell Survival guide][5]
  A large list of resources to get you started, compiled by the community.
- [PowerScripting podcast][4]
  If you have some time during you commute or any other activity that
  allows you to listen to some audio I highly recommend this show. The
  show notes are of a great quality, and contain lots of links to
  learning resources. The first shows take you step
  by step through the process of learning [PowerShell][1]. 

### (e-)Books

- [Effective Windows PowerShell][7]
  A great set of tips, explanations to be as the title suggests
  effective with [PowerShell][1].
- [Master-PowerShell][6]
  A very comprehensive free e-book starting with the basics and ending
  with a guide to remoting.   
- [Windows PowerShell in Action, Second Edition][3]
  This is in my opinion the [PowerShell][1] book available today that
  is the best suited for developers. It goes into all the details of
  the language and is very well written. Be sure to get the (recently)
  released second edition, since it is filled with loads of extra
  content covering the [PowerShell][1] version 2 features.


## Just use PowerShell instead of cmd
When learning something new it is always nice to be able to start with
something familiar. The beauty of [PowerShell][1] is that all your
previous knowledge about your favorite command-line tools are not
lost. [PowerShell][1] is a shell which means you can use it to start
any of tool you used to start in cmd. Moreover the [PowerShell][1]
team has incorporated a large number of [aliases][8] that should be
familiar to you whether you are coming from a linux or cmd background
the commands you know like `dir`, `ls`, `cd`, `del`, `rm` all work as you
would expect. These aliases are also very handy for those who don't
like to type long commands at the prompt. To get an idea of what
aliases are available try the following:

<script type="syntaxhighlighter" class="brush: ps"><![CDATA[
PS> dir alias: | Out-Host -Paging
]]>
</script>

Using [PowerShell][1] as your preferred shell gives you the
opportunity to gradually learn [PowerShell][1] and just
lookup/research stuff as you use it in your day to day work.

## The 3 amigo's of discovery 
When learning [PowerShell][1] I've found that the most helpful and
best [Cmdlets][9] are the following three.

### Get-Help
[`Get-Help`][10] does exactly what you would expect especially when you know
it's aliases: `man`, `help`. You can get the help on help by typing `help`
at the prompt. This shows you how you can use [`Get-Help`][10]. Note
that [PowerShell][1] also comes with topical help pages that start
with `about_` to get an overview of the available topics type: 

<script type="syntaxhighlighter" class="brush: ps"><![CDATA[
PS> help about_*
]]>
</script>
 at the [PowerShell][1] prompt.

### Get-Command
[`Get-Command`][11] provides a way to search for a Cmdlet you would
like to use. Looking at the output of `help Get-Command` or shorter
`Get-Command -?` you will see that one of the parameter sets contain
the `-Noun` and `-Verb` parameters. The naming convention used for
Cmdlets is `<Verb>-<Noun>` this makes remembering and searching the
Cmdlets a lot easier. Say for instance I would like to know all
Cmdlets that remove stuff then 

<script type="syntaxhighlighter" class="brush: ps"><![CDATA[
PS> Get-Command -Verb remove
]]>
</script>
will list them nicely. If I would like to know what Cmdlets are available for
working with computer objects, I would type: 
<script type="syntaxhighlighter" class="brush: ps"><![CDATA[
PS> Get-Command -Noun Computer
]]>
</script> 

### Get-Member
[`Get-Member`][13] list all member that is public methods and properties
of the object passed to it. This ideal for finding what information
can be extracted from an object, what you can do with a specific
object respectively. To for instance lookup what properties you could
use on a file to sort in a directory listing you could type 

<script type="syntaxhighlighter" class="brush: ps"><![CDATA[
PS> dir | Get-Member
]]>
</script>
Or if you don't want to wait on a slowly loading MSDN page to lookup
what methods are available to you on a [`TimeSpan`][14] object you
could use something like:

<script type="syntaxhighlighter" class="brush: ps"><![CDATA[
PS> New-Object TimeSpan | Get-Member 
]]>
</script>

Or if you can't remember the way `SubString` works type:

<script type="syntaxhighlighter" class="brush: ps"><![CDATA[
PS> ""| gm
]]>
</script>
where `gm` is the (shorter) alias for [`Get-Member`][13].

I hope this provides enough pointers to guide you through your first
steps to [PowerShell][1] mastery. Check back soon for part 2 of
[this series][12] when we dive in to the [PowerShell][1] language as
viewed through the eyes of a C# developer.

{% include date.inc %}

<h5 id="references">References</h5>
<div class="references">
<ul>
<li><a href='/2011-06-19/ps4.netdevs-0-what-and-why/' title='PS for .NET devs part 0: PowerShell what is it and why should I care?'>PS for .NET devs part 0: PowerShell what is it and why should I care?</a></li>
<li><a href='http://technet.microsoft.com/en-us/scriptcenter/dd742419' title='Scripting with Windows PowerShell'>Technet: Scripting with Windows PowerShell</a></li>
<li><a href='http://powershell.ourtoolbar.com/' title='PowerShell Community Toolbar'>PowerShell Community Toolbar</a></li>
<li><a href='http://www.manning.com/payette2/' title='Windows PowerShell in Action'>Windows PowerShell in Action</a></li>
<li><a href='http://powerscripting.net/' title='PowerScripting Podcast'>PowerScripting Podcast</a></li>
<li><a href='http://social.technet.microsoft.com/wiki/contents/articles/windows-powershell-survival-guide.aspx#Learning_Resources' title='Windows PowerShell Survival Guide'>Windows PowerShell Survival Guide</a></li>
<li><a href='http://powershell.com/cs/blogs/ebook/' title='Master-PowerShell'>Master-PowerShell</a></li>
<li><a href='http://rkeithhill.wordpress.com/2009/03/08/effective-windows-powershell-the-free-ebook/' title='Effective Windows PowerShell'>Effective Windows PowerShell</a></li>
<li><a href='http://technet.microsoft.com/library/dd347645(en-us).aspx' title='About Aliases'>About Aliases</a></li>
<li><a href='http://msdn.microsoft.com/en-us/library/ms714395(v=VS.85).aspx' title='Cmdlet Overview'>Cmdlet Overview</a></li>
<li><a href='http://go.microsoft.com/fwlink/?LinkID=113316' title='Get-Help online help'>Get-Help online help</a></li>
<li><a href='http://go.microsoft.com/fwlink/?LinkID=113309' title='Get-Command online help'>Get-Command online help</a></li>
<li><a href='/tags/ps4.netdevs.html' title='PS for .NET devs category'>PS for .NET devs category</a></li>
<li><a href='http://go.microsoft.com/fwlink/?LinkID=113322' title='Get-Member online help'>Get-Member online help</a></li>
<li><a href='http://msdn.microsoft.com/en-us/library/system.timespan.aspx' title='msdn: TimeSpan'>msdn: TimeSpan</a></li>
</ul>
</div>
[0]: /2011-06-19/ps4.netdevs-0-what-and-why/ "PS for .NET devs part 0: PowerShell what is it and why should I care?"
[1]: http://technet.microsoft.com/en-us/scriptcenter/dd742419 "Scripting with Windows PowerShell"
[2]: http://powershell.ourtoolbar.com/ "PowerShell Community Toolbar"
[3]: http://www.manning.com/payette2/ "Windows PowerShell in Action"
[4]: http://powerscripting.net/ "PowerScripting Podcast"
[5]: http://social.technet.microsoft.com/wiki/contents/articles/windows-powershell-survival-guide.aspx#Learning_Resources "Windows PowerShell Survival Guide"
[6]: http://powershell.com/cs/blogs/ebook/ "Master-PowerShell"
[7]: http://rkeithhill.wordpress.com/2009/03/08/effective-windows-powershell-the-free-ebook/ "Effective Windows PowerShell"
[8]: http://technet.microsoft.com/library/dd347645(en-us).aspx "About Aliases"
[9]: http://msdn.microsoft.com/en-us/library/ms714395(v=VS.85).aspx "Cmdlet Overview"
[10]: http://go.microsoft.com/fwlink/?LinkID=113316 "Get-Help online help"
[11]: http://go.microsoft.com/fwlink/?LinkID=113309 "Get-Command online help"
[12]: /tags/ps4.netdevs.html
[13]: http://go.microsoft.com/fwlink/?LinkID=113322 "Get-Member online help"
[14]: http://msdn.microsoft.com/en-us/library/system.timespan.aspx "msdn: TimeSpan"

