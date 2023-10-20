If you know someone who is slightly geeky and always seems to be that bit
more in touch with what’s going on in the world that you are, then they are
probably using RSS feeds to keep themselves up to date.

But fortunately, you don’t need to be a geek to make use of RSS feeds. In
this article, Dave Cross explains what they are and how to use them.

## What is an RSS Feed?

An RSS feed is nothing more complicated than a file which someone makes
available for other people to download over the internet. In that way it’s
really not that different from a standard web page. The difference is that
whilst your web page can pretty much look however you want, an RSS feed needs
to stick to far stricter rules about what it contains. The reason for this
is that RSS feeds aren’t really intended to be read by humans, they are meant
to be processed by computers.

Someone who wants to read and RSS feed needs a program called an RSS reader.
This program understands the format of an RSS feed and can convert into a
format which the user can read. The clever thing is that the user can
subscribe to any number of RSS feeds and, because their format is
standardised, the same RSS reader program can read all of them and display
them all in the same way. This is your geeky friends secret – he’s getting
all his information from RSS feeds.

We’ll look in how that all works in a bit more detail later on, but first
let’s look at the kinds of information that you can get from RSS.

## What Can You Get From an RSS Feed?

An RSS feed basically contains a list of pieces of information. Each piece
of information in the list contains a title, a web link and (optionally)
a longer description. There are many other attributes that each item can
have, but those are the important three.

The increased interest in RSS was largely driven by the weblog (or ‘blog’)
explosion over the last few years. Many blogs take the form of an online
diary and these fit in very well with the RSS format. Each blog entry has
a title, a web link (the address of the entry on the original web site) and
a longer description (the contents of the entry). So if you have a dozen or
so blogs that you like to read regularly and they all produce RSS feeds then
you can plug their addresses into your RSS reader and read all of them easily
each day without having to visit a dozen individual web sites. Also, most
popular blogging tools have RSS support as one of their standard features, so
if you are blogging using Movable Type, Blogger, Word Press or pretty much
any other major blogging tool then you’re producing an RSS feed
automatically already and making it easier for people to read your entries.

After RSS had taken off in the blog world, the next area that where it became
popular was in news publication. News stories have the same basic structure as
a blog entry. They have a title, a web link (back to the story on a news web
site) and a longer description (the text of the story). It’s therefore no
surprise that some of the biggest news sites on the web were amongst the next
wave of people to start publishing RSS feeds. These days you can get RSS
feeds from a number of newspaper web sites, as well as from news broadcasters
like the BBC and CNN.

But that’s not all you can get in RSS. Any information that can be boiled
down to a title and a web link can be published in a RSS feed. Looking down
the list of 170-odd RSS feeds that I’m subscribed to, the vast majority of
them are blogs or newsfeeds, but there are a number of other type of
information. One site publishes new London restaurant reviews in RSS, another
publishes the results of automatic tests of software that I write, another
gives me a five day weather forecast. Google’s email service, Gmail, allows
you to subscribe to a feed showing when you have new mail waiting. The photo
sharing service Flickr gives me feeds showing when my friends have uploaded new
photos or when someone comments on one of my photos. Every day someone comes up
with new types of information to share with RSS. And all of this data appears
in the same way in my RSS reader.

## Reading RSS Feeds

Hopefully that list has whetted your appetite and you’re now keen to start
reading RSS feeds. To do that you need to find an RSS feed reader. There are
many of these available for all computing platforms. There is [a good list of
them on Wikipedia](http://en.wikipedia.org/wiki/List_of_news_aggregators).

Personally, I like to use a web-based RSS reader and I currently use
[Bloglines](http://www.bloglines.com/). To get an idea of what it looks like
you can visit my public list of subscribed RSS feeds at
http://www.bloglines.com/public/davorg. You’ll see a list of my RSS feeds
in the left-hand pane. Clicking on any of the feeds will display a list of
the most recent items from that feed in the right-hand pane. The main title
of each feed is a link to the site that supplies the feed and the title of
each individual item is a link to that story on the originating web site.
Hopefully that’s all pretty obvious.

Now, of course, you could just read the feeds that I subscribe to but it’s
unlikely that your interests will be the same as mind and you’ll get far
more use out of Bloglines if you sign up yourself. You can register for a
free account from the front page or from the “register” link in the top
right-hand corner of every page. Once you have registered and signed in you
can start to add your favourite feeds to your own list. Once you have some
feeds in your list, clicking on the ‘xxx feeds’ link at the top of the list
will display all of the new items in all of your feeds in the right-hand
pane.

## Finding Feeds to Read

So how do you go about finding interesting feeds to subscribe to? It’s
probably best to look at the problem from the opposite direction. You already
know which web sites have interesting content that you like to read, so it’s
just a question of finding which of those publish an RSS feed.

More and more web sites are advertising the fact that they publish RSS.
You’ll often see a small orange icon containing the abbreviation ‘RSS’
or ‘XML’ (RSS is a kind of XML). This will be a link to the RSS version
of the current page. If you right-click on this icon you will be able to copy
the “link location” into your clipboard. You can then paste the link into
the “blog or feed url” field in the Bloglines “add feed” form. You can then
subscribe to the feed. Sometimes sites don’t use the orange icon, but they’ll
usually have some other method to indicate the location of the feed file. For
example, [Guardian Unlimited](http://www.guardian.co.uk/) has a link entitled
“web feed” about halfway down the left-hand column which links to the RSS feed.

There is, however, another, easier, way to find an RSS feed from a web page
that you like. This is called “autodiscovery” and it is supported by most RSS
readers, including Bloglines. To use autodiscovery, you don’t need to find
out the location of the RSS file, you simply give your RSS reader the address
of the web page and the RSS reader will search the page for any RSS links
that it can find. It will then present you with a list of feeds found (with
some kind of description of what eash feed is) and allow you to choose one
(or more) to subscribe to. For example, the address of the Guardian Unlimited
front page is http://www.guardian.co.uk/. If you put that address into the
“blog or feed url” field in the Bloglines “add feed” form, then Bloglines
will find the feed address hidden within that page and let you subscribe to
that.

This is often the easiest way to subscribe to an RSS feed. Of course,
sometimes you’ll find that the page you are interested in doesn’t contain an
RSS feed. In that case you’re out of luck (but you should consider
contacting the owner of the site suggesting that they publish a feed). If
you’re using the Firefox web browser then it gets even easier. The Bloglines
team have produced an extension for Firefox which you can get from
http://www.bloglines.com/help/firefox. With this extension installed,
subscribing to a page becomes as simple as right-clicking on the page and
selecting “subscribe to this page” from the Bloglines toolkit menu which
will appear.

Sometimes a single page will have multiple RSS feeds available. This can be
for various reasons. Firstly their are a number of slightly different RSS
formats (and another format called Atom which does much the same thing) so
you’ll often see the same the feed appearing in more than one format (look
for different file extensions like .rss, .rdf and .xml). Which one you choose
is really a matter of personal preference. Another common difference is
between feeds which publish the full text of an item and those which only
publish an extract. With this second type you need to go back to the original
web page to read the whole item. This is particularly common if the original
site like to serve you lots of adverts! Personally, I always choose a full
text version if it’s available.

## Conclusion

That’s how simple it is to start to use RSS. You too can become one of those
people who are always up to date with the latest news.

In forthcoming articles, we’ll look in more detail at RSS. In particular,
how to incorporate the data from an RSS feed into your web site and how to
publish your own RSS feeds.
