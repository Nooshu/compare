# Compare HAR files
Make it easier to find regressions by comparing your [HAR](http://www.softwareishard.com/blog/har-12-spec/) files. Test it out https://compare.sitespeed.io or look at the video: https://youtu.be/dCThwpglIeE

![Logo](https://raw.githubusercontent.com/sitespeedio/compare/master/img/compare.png)

## First: Shout out!
We couldn't built compare without the support or inspiration from the following people:
 * Thank you [Michael Mrowetz](https://twitter.com/MicMro) :bow: for creating [PerfCascade](https://github.com/micmro/PerfCascade) (the SVG HAR waterfall viewer).
 * Thank you [Patrick Meenan](https://twitter.com/patmeenan) :bow:. Pat has built the HAR compare viewer in [WebPageTest](https://www.webpagetest.org/) that inspired us to the idea with the slider.

If you like our project, please give them also some extra love :)

## Comparing
![Compare two different HAR files](https://raw.githubusercontent.com/sitespeedio/compare/master/docs/img/compare.png)

## How it works
As long as your HAR files follow the [HAR specification](http://www.softwareishard.com/blog/har-12-spec/) you can use them in Compare. Standard HARs will give you some basic functionality and HARs from WebPageTest and sitespeed.io will give you more.

### HARs from Firefox/Chrome/Safari (and other browsers).
For all HARs we will show the waterfall (using [PerfCascade](https://github.com/micmro/PerfCascade)) and statistics for the page (using [PageXray](https://github.com/sitespeedio/pagexray)).

### WebPageTest
If you add a [WebPageTest](https://www.webpagetest.org) HAR we will show SpeedIndex and FirstVisualChange and if you used Chrome to collect CPU stats, we will show that too. You will get some extra sugar if your HAR is from WebPageTest! Do you have something else that we should add? Create an issue or send a PR!

### sitespeed.io/Browsertime
If you want even more sugar, you should use HAR files from [sitespeed.io](https://github.com/sitespeedio/sitespeed.io) or [Browsertime](https://github.com/sitespeedio/browsertime): SpeedIndex, FirstVisualChange, LastVisualChange and a graph for VisualProgress.

If you deploy your result from your sitespeed.io run to a server and use **--resultBaseURL** when you run sitespeed.io, we will also pickup the screenshot, video and a link to the result page.

If you also run with **--firstParty** (adding a regex that show which assets that are first/third parties) we will will show data grouped by party.

![First Party vs Third Party!](https://raw.githubusercontent.com/sitespeedio/compare/master/docs/img/firstparty.png)

## How to use it
You can either upload two HAR files (drag/drop) or give the URL to two URLs hosted online.

If you host your sitespeed.io result pages, you can copy/paste the URL to a page or to a specific run and Compare will automagically find the URL to the HAR file.

### Compare on the fly
You can also compare two HAR files on the fly that are available on the internet. Add the parameters **?har1=FULL_URL1&har2=FULL_URL2&compare=1** and the two HAR files will be compared.

### Github gist
You can also use host your URLs on a [Github gist](https://gist.github.com/) with the following format:

```json
{
  "har1": {
    "url": "https://www.url.com/browsertime1.har",
    "label": "Before change"
  },
  "har2": {
    "url": "https://www.url.com/browsertime2.har",
    "label": "After change"
  },
  "comment": "Checkout the problem on with the 1st request after the change, it doesn't look good!"
}
```
Labels and the comment are optional.

And then use it with: https://compare.sitespeed.io?gist=GIST_ID

You can checkout out our example:
[https://gist.github.com/soulgalore/94e4d997a78e03b32b939fcea63eae8e](https://gist.github.com/soulgalore/94e4d997a78e03b32b939fcea63eae8e)

Thank you [Matt Hobbs](https://github.com/Nooshu) for sharing the gist idea!

## How to contribute a.k.a what are we looking for?
Send us a PR/create an issue. If you have big change coming up, please discuss it with us in an issue first.

## Deploy your own version
Deploying your own version is easy:
1. Clone the repo: `git clone git@github.com:sitespeedio/compare.git`
2. Build: `cd compare && npm run build`
3. Copy everything in *build/* to your server

### Be kind
If you deploy your own version: please keep the original logo and the link to the project. We have spent a lot of our free time to work on this!

## The logo
The compare logo (and the rest of the sitespeed.io logos) are made by [Mochamad Arief](https://twitter.com/mochawalk),
you can find his stuff at http://www.mochawalk.com/.
