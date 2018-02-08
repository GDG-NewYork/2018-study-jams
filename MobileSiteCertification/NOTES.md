# Mobile Site Certification Study Jams

## [GDG NYC Study Jam](http://bit.ly/gdgnyc-cloud-studyjams-2018)

The [Mobile Site Certification Study Jams](http://bit.ly/gdgnyc-cloud-studyjams-2018) is a community initiative to encourage members to learn & assess their knowledge of best practices for web site development.

 * Mobile Site Certification is a professional accreditation offered by Google
 * Focus is on demonstrating understanding of basic & advanced concepts in mobile website design & development
 * [Certification Requirements](https://academy.exceedlms.com/student/path/2967) are managed by the _Academy of Ads_
 * Assessment (exam) takes 90 minutes and has 65 questions.
 * [Academy Study Guide](https://academy.exceedlms.com/student/path/2967) has about 13 sections (~2hrs) of review content.
 * [Google Partners Guide](https://support.google.com/partners/answer/7327828) has 4 modules (time not provided.)
 * Join the [GDG NYC Slack](https://gdgny.slack.com) on the _#2018-mobile-site-cert_ channel to share insights or discuss issues.

<br/>
## [Academy Study Guide](https://academy.exceedlms.com/student/path/2967)

_Study Notes from the Academy Guide "[Study Mobile Sites](https://academy.exceedlms.com/student/path/2967)" section. Participants are encouraged to review the content on the site directly, and use this only for quick recaps or reviews as needed._

``` 
1. WIN CUSTOMERS WITH MOBILE SITES (9 min)
```

**Takeaway:** _Faster mobile sites with better UX can drive more conversions_

Why "mobile" web sites?

 * Mobile device usage is rising
 * Mobile sites are easily discoverable (no app installs)
 * Generally have a lower dev cost, higher usability & simple tracking

As a business owner, some reasons why your web site may underperform on mobile:
 
 * Slow page loads (e.g., initial load, rich media usage)
 * Poor user experience design (e.g., unclear workflows)
 * Network constraints (e.g., bandwidth limitations, offline access)

Underperfomance leads to fewer conversion events on mobile (vs. desktop).
Optimize mobile web sites for speed & user experience!

> RESOURCES

 * [Industry benchmarks for Mobile Page Speed](https://www.thinkwithgoogle.com/articles/mobile-page-speed-new-industry-benchmarks.html)
 * [Think With Google: Designing better UX for Shoppers](https://www.thinkwithgoogle.com/marketing-resources/experience-design/mobile-retail-apps-and-sites-designing-better-experience-for-shoppers/)

``` 
2. CUT LOAD TIMES WITH DEVELOPER TOOLS (12 min)
```

**Takeaway:** _Chrome DevTools can help identify issues with website performance (e.g., first load time, page render time)_

You may notice that some pages on your website load slowly, causing customers to abandon the page prematurely (lowers conversions). How can you pinpoint problems?

**Inspecting with Chrome DevTools**

 * Network tab / Click camera to capture screenshots
 * Switch to mobile device view / Select 3G Network / Disable cache
 * How long does it take for page to load (under this slow network condition)
 * Which parts of page slowed this down (check waterfall diagram)

Usual culprits

 * Large images: can you replace with smaller options or SVG?
 * Parser blocking JS: can you mark scripts "async" for background execution?
 * Script loaded first: can you move script to end of <body> tag to load rest of HTML before script is reached?

Note: by [PWA Guidelines](https://developers.google.com/web/progressive-web-apps/#fast) a site that takes more than 3 seconds to load will likely lose 50% of its visitors.
    
> Let's talk about the *render tree*.

This is the process by which browser 
  * Receives page "bytes" (raw data) from the server
  * Converts bytes to code = into meaningful DOM (document object model) and CSSOM (CSS object model) entities
  * Relates HTML/DOM to CSS/CSSOM to build "render tree" (= identifies rules)
  * Places objects onscreen (= enforces rules) and creates the visual page

Rendering objects onscreen is expensive. Your choice of page layout can have a huge impact on performance by deciding how much (and how often) different parts of the screen needs to be repainted -- especially if you add animations -- on "reflows" (e.g., when screen orientation changes).

To fix this, evaluate the _critical rendering path_ for your website.

**Inspecting with Chrome DevTools:**

 * Go to the Performance tab (was "Timeline" tab)
 * Record/Profile the session - then check Event Logs
 * Filter by terms (e.g. "Parse HTML", "Recalculate Style") to see time taken for rendering (DOM creation, CSSOM creation respectively) - and identify places where fixes are needed
 * Look at highest-cost and highest-aggregated-cost events for better understanding of where performance bottlenecks are.

> RESOURCES

 * [Chrome Dev Tools | Network Performance](https://developers.google.com/web/tools/chrome-devtools/network-performance/)
 * [Udacity | Web Performance Optimization](https://www.youtube.com/playlist?list=PLAwxTw4SYaPmKmNX-INgcxQWf30KuWa_A)

  
``` 
3. SPEED UP MOBILE SITE RENDERING  (7 min)
```

**Takeaway:** _ _

``` 
4. KEY METRICS FOR TESTING YOUR SITE (9 min)
```

**Takeaway:** _ _

``` 
5. OPTIMIZE MOBILE SITE TRANSFER SIZE (7 min)
```

**Takeaway:** _ _

``` 
6. OPTIMIZE IMAGES AND FONTS (12 min)
```

**Takeaway:** _ _

``` 
7. FOCUS ON MOBILE USER EXPERIENCE (7 min)
```

**Takeaway:** _ _

``` 
8. DELIVER USER-CENTERED MOBILE EXPERIENCES (8 min)
```

**Takeaway:** _ _

``` 
9. MAKE MOBILE SITES THAT DRIVE CONVERSIONS (8 min)
```

**Takeaway:** _ _

``` 
10. TEST AND OPTIMIZE MOBILE EXPERIENCES  (7 min)
```

**Takeaway:** _ _

``` 
11. CREATE SUPER FAST SITES WITH AMP  (7 min)
```

**Takeaway:** _ _

``` 
12. CREATE PROGRESSIVE WEB APPS  (8 min)
```

**Takeaway:** _ _

``` 
13. ENGAGE USES WITH APIS (7 min)
```

**Takeaway:** _ _

<br/>
## [Google Partners Study Guide](https://support.google.com/partners/answer/7327828)

_Study Notes from the [Google Partners Study Guide](https://support.google.com/partners/answer/7327828). Participants are encouraged to review the conent on the site directly, and use this only for quick recaps or reviews as needed._



### Module 1 | Mobile Sites & Why They Matter

```
1.1 BASICS OF MOBILE SITES
```

```
1.2.1 USER EXPECTATIONS
```

```
1.2.2 IMPACT OF CONVERSIONS AND INTERACTION
```

```
1.2.3 WHY UX MATTERS
```

```
1.3 DISCOVERABILITY
```



### Module 2 | Improving Mobile Site Speed

```
2.1.1 TOOLS TO GET STARTED
```

```
2.1.2 UNDERSTANDING LOW BANDWIDTH AND HIGH LATENCY
```

```
2.1.3 TARGETS TO FOCUS ON
```

```
2.2 CRITICAL RENDERING PATH
```

```
2.2.1 CONSTRUCTING THE DOCUMENT OBJECT MODEL
```

```
2.2.2 THE RENDER TREE
```

```
2.2.3 THE LAYOUT
```

```
2.2.4 ANALYZING THE ENTIRE CRP IN DEV TOOLS
```

```
2.2.5 OPTIMIZING THE CRITICAL RENDERING PATH
```

```
2.3 OPTIMIZE CONTENT EFFICIENCY
```

```
2.3.1 ELIMINATE UNNECESSARY DOWNLOADS
```

```
2.3.2 OPTIMIZING ENCODING AND TRANSFER SIZE
```

```
2.3.3 IMAGE OPTIMIZATION
```

```
2.3.4 WEBFONT OPTIMIZATION
```

```
2.3.5 HTTP CACHING
```

### Module 3 | Creating an effective mobile UX

```
3.1 UX PRINCIPLES
```

```
3.1.1 ASSESS YOUR MOBILE SITE
```

```
3.1.2 LEARN WHAT MAKES A GOOD MOBILE SITE
```

```
3.2 MOBILE SITE DESIGN BEST PRACTICES
```

```
3.2.1 HOMEPAGE AND SITE NAVIGATION
```

```
3.2.2 SITE SEARCH
```

```
3.2.3 COMMERCE AND CONVERSIONS
```

```
3.2.4 FORM ENTRY
```

```
3.2.5 USABILITY AND FORM FACTOR
```

```
3.3 TESTING AND MEASURING SUCCESS
```

```
3.3.1 A/B TESTING
```

```
3.3.2 MEASURING SUCCESS WITH GOOGLE ANALYTICS AND METRICS TO FOCUS ON
```

### Module 4 | Advanced Web Technologies

```
4.1 INTRODUCTION TO ACCELERATED MOBILE PAGES
```

```
4.1.1 WHAT IS AMP
```

```
4.1.2 HOW AMP WORKS
```

```
4.2 INTRODUCTION TO PROGRESSIVE WEB APPS
```

```
4.2.1 INTRODUCTION TO THE APP SHELL ARCHITECTURE
```

```
4.2.3 INTRODUCTION TO SERVICE WORKERS
```

```
4.3 USER ENGAGEMENT AND APIS
```

```
4.3.1 INTRO TO WEB PUSH AND NOTIFICATIONS
```

```
4.3.2 PAYMENT INTEGRATION
```