autoscale: true
build-lists: true

## [fit] Web Accessibility 101:<br> Why It Matters
### with Stephanie Marx

---

## About Me
### Graduate of IIT and Dev Bootcamp
### Web Developer at UL

^ graduate of IIT with psych degree and most of a physics degree, ask me about that some other time

^ graduate of dev bootcamp, a 19-week program that turns everyday folks into web developers

^ UL is a 122-year-old global safety consulting and certification company based on Northbrook

^ my team is 10 people, create internal and external-facing applications for engineers, product manufacturers, trade associations, and consumers

^ my position is full stack in Ruby on Rails. I specialize on the very front of the front end (HTML/CSS) and design (UI/UX) and i have a passion for accessibility


---

# This talk is about...
- how we define accessibility
- different types of disabilities
- how to make the web more accessible


---

# [fit] Show of hands...

^ raise your hand if you’ve written any html

^ if you’re written any css

^ if you have made a visual design for the web (wireframe, mockup, etc)

^ if you’ve made a code or design choice specifically for accessibility

---

# [fit] My Goal

^ that you’ll leave this talk with some good ideas that you can implement in your own code, and with the knowledge to go and learn even more.

^ also to make this talk as accessible as i can, please let me know if i’m speaking too quickly, too quietly, if I’m using too much jargon, or my presentation slides aren’t visible or readable.

^ to that end, i'll be putting up my slides and some additional notes on my site later today. i'll give you the link when we're done

^ also, i'm leaving time for questions at the end, but if you have a burning question or need some clarification, just raise your hand and i'll get to you.

---

# [fit] What is accessibility <br> and why does it matter?

^ To understand accessibility, we first need to understand a bit about disability. There are five general categories of disabilities that we need to think about when designing for the web.

^ This isn't meant be a completely exhaustive list, instead think of this as a starting point for understanding.

---

# Categories of disabilities
- visual
- hearing
- motor
- cognitive
- seizure

^ 5 major categories of disability types that we’ll address in this talk
  - visual - blindness, low-vision, color-blindness
  - hearing - deafness and hard-of-hearing
  - motor - Parkinson’s, cerebral palsy, muscular dystrophy: cause inability to use a mouse, slow response time, limited fine motor control
  - cognitive - Dyslexia, global developmental delay, autism, Down’s syndrome,  learning disabilities, distractibility, inability to remember or focus on large amounts of information
  - seizure - seizures caused by strobing, flickering, or flashing effects

^each of the major categories requires certain types of adaptations in the design of web content. most of the time, these adaptations benefit nearly everyone, not just people with disabilities.
  - helpful illustrations! clear navigation!
  - captions are needed for deaf users, and can people helpful to people who view a video without audio

---

## Why create accessible content?

^ 1 in 5 americans have a disability. no sensible person could make an ethical or economical argument for potentially excluding 20% of their audience. you wouldn't design a website to not work on 20% of browsers used by your audience, would you?  

^ why create accessible web content?

^ there are all acceptable motivations! some are just more or less altruistic than others.there are all acceptable motivations! some are just more or less altruistic than others.
  - to improve the lives of people with disabilities
  - to capitalize on a wider audience or consumer base
  - to avoid lawsuits and/or bad press

---

# Major Laws

^ Americans with Disabilities Act
  - 1990, civil rights legislation from DOJ
  - not directly about the internet, but works to ensure that people with disabilities have equal opportunities

^ Rehabilitation Act of 1973
  - prohibits discrimination on the basis of disability in programs run by federal agencies; programs that receive federal financial assistance; in federal employment; and in the employment practices of federal contractors.

^ many international laws

---

## Web Content Accessibility Guidelines 2.0
### by the Worldwide Web Consortium

^ Web Content Accessiblity Guidelines 2.0, published in Dec 2008

^ developed with W3C (Worldwide Web Consortium), the governing body of the web

^ guidelines that are the basis of most web accessibility law in the world

---

# Four Principles
- Perceivable
- Operable
- Understandable
- Robust

^ so, the W3C created four principles that define accessibility

^ based on four principles
  - perceivable - available to the senses either through browser or other assistive technologies (screen readers, screen enlargers, etc)
  - operable - users can interact with all controls and interactive elements using either the mouse, keyboard, or an assistive device
  - understandable - content is clear and limits confusion and ambiguity
  - robust - a wide range of technologies (including old and new user agents and assistive tech) can access the content

---

# [fit] So how do we do this?

^ web accessibility is easy! once you understand how important it is and learn the techniques for making content accessible, it’s relatively easy to do.

^web accessibility is a process. an accessible site doesn’t happen overnight, and i know i’m always finding new things i can do to make the sites i work on more accessible. it’s not something to achieve, but something to always strive for.

^so, what are some things that make our sites less accessible, why do they matter, and how can we fix them? i have about a dozen or so examples, which are just a small sample of common accessibility issues.

---

## Document Language Missing

```html
<!DOCTYPE html>
<head>
  <meta charset="utf-8">
  <title>Web Accessibility 101</title>
</head>
<body>
</body>
</html>
```

^ what it means: the language of the document isn’t identified

^ why it matters: identifying the language of the page allows screen readers to read the content in the appropriate language. it also facilitates automatic translation of content.

^ how to fix it: identify the document language using the <html lang=“en”> attribute (or whatever non-english language)

---

## Document Language - Fixed!
```html
<!DOCTYPE html>
<html lang="en-US">
<head>
  <meta charset="utf-8">
  <title>Web Accessibility 101</title>
</head>
<body>
</body>
</html>
```

---

## Missing Form Label
```html
<input type="text" name="firstname" placeholder="First Name">
```

![inline](/Users/stephaniemarx/Desktop/Screen Shot 2016-04-30 at 12.08.37 AM.png)

^ what it means: a form control doesn’t have a corresponding label

^ why it matters: if a form control doesn’t have a properly associated text label, the function or purpose of that form control may not be presented to screen reader users. form labels also provide visible descriptions and larger clickable targets.

^ how to fix it: if a text label is visible for a form control, use the <label> element to associate it with its respective form control. if there isn’t a visible label, either add a label or add a descriptive title attribute to the form control

---

## Form Label - Fixed!

```html
<label for="firstname">First name:</label>
<input type="text" name="firstname" placeholder="First Name">
```

![inline](/Users/stephaniemarx/Desktop/Screen Shot 2016-04-30 at 12.10.55 AM.png)

---

## Missing First Level Heading

```html
<p>Stephanie's Blog</p>
<p>This is my site, it's pretty great.</p>
```

^ what it means: a page doesn’t have a first level heading, <h1>

^ why it matters: headings facilitate navigation for users of many assistive technologies. they also provide semantic and visual meaning, as the h1 is the most important heading of the page.

^ how to fix it: if the page presents a main heading, place it in a <h1> element

---

## Missing First Level Heading - Fixed!

```html
<h1>Stephanie's Blog</h1>
<p>This is my site, it's pretty great.</p>
```

---

## Skipped Heading Levels

```html
<h1>Stephanie's Blog</h1>
<h2>This is my site, it's pretty great.</h2>
<h4>Things to know about me:</h4>
<ul>
  <li>I own two gerbils.</li>
  <li>I like board games.</li>
<ul>
<h5>Thanks for visiting!</h5>
```

^ what it means: a heading level is skipped

^ why it matters: headings provide document structure and facilitate keyboard navigation by users of assistive tech. these users may be confused or experience difficulty navigating when heading levels are skipped.

^ how to fix it: restructure the document headings to ensure that heading levels are not skipped.

---

## Skipped Heading Levels - Fixed!

```html
<h1>Stephanie's Blog</h1>
<h2>This is my site, it's pretty great.</h2>
<h3>Things to know about me:</h3>
<ul>
  <li>I own two gerbils.</li>
  <li>I like board games.</li>
<ul>
<h4>Thanks for visiting!</h4>
```

---

## Missing Alternative text

```html
<img src="gerbil.png">

```

^ what it means: image alt text is not present

^ why it matters: each image must have an alt attribute. without alt text, the content of an image will not be available to screen reader users or when the image is unavailable.

^ how to fix it: add an alt attribute to the image. the attribute value should accurately and succinctly present the content and function of the image. if the content of the image is converting in the context or surroundings of the image, or if the image does not convey content or have a function, it should be given an empty/null alt text aka alt=“"

---

## Missing Alternative Text - Fixed!

```html
<img src="gerbil.png" alt="white gerbil on wheel">
```

![inline](/Users/stephaniemarx/Desktop/IMG_20160413_212424.jpg)

---

## Blinking Content

```html
<blink>This text is going to blink!</blink>
```

```css
.blinking-text {
  text-decoration: blink;
}
```


^ what it means: blinking content is present

^ why it matters: blinking content can be distracting and confusing to users, particularly those with certain cognitive disabilities. it can also cause serizures in people with epilepsy and related conditions.

^ how to fix it: removing the blinking effect (<blink> element or text-decoration: blink style) or fast-moving, blinking gifs or videos.

---

## Link to a Document

```html
<a href="schedule.doc">Tournament Schedule</a>
<a href="accessibility.ppt">Accessibility Presentation</a>
<a href="passwords.xls">Passwords in Plain Text</a>
<a href="invite.pdf">Wedding Invite</a>
```

^ what it means: a link to a document is present

^ why it matters: unless authored with accessibility in mind, MS word docs often have accessibility issues. additionally, word documents are typically viewed in a separate application, and can cause confusion and navigation difficulties.

^ how to fix it: ensure that the word doc is natively accessible. additionally, inform the user that the link will open a word document. html content should usually be used in place of or in addition to a word doc.

^ this also applies to powerpoint presentations, excel docs, pdf, most non-html documents

---

## Justified Text

![inline](justified.png)\

^ what it means: fully justified text is present

^ why it matters: large blocks of justified text can negatively impact readability due to varying word/letter spacing and ‘rivers of white’ that flow through the text

^ how to fix it: remove the full justification from the text

---

## Justified Text - Fixed!

![inline](left-align.png)

---

## Audio/Video Content

^ what it means: an audio or video file is present

^ why it matters: audio content must be presented in a text format to be fully accessible to users who are deaf and hard of hearing. video content with audio must have synchronized captions and a transcript. audio-only content must have a transcript.

^ how to fix it: (ensure the above)

---

## Small Text

#### wow so tiny

^ what it means: text is very small (less than 10px)

^ why it matters: text which is very small is difficult to read, particularly for those with low vision.

^ how to fix it: increase the text to a more readable size.

---

## Low Color Contrast
![inline](contrast.png)

^ what it means: very low contrast between foreground and background colors

^ why it matters: adequate contrast is necessary for all users, especially users with low vision

^ how to fix it: increase the contrast between the foreground (usually text) color and the background color. large text (larger than 18 point or 14 point bold) does note require as much contrast as smaller text.

---

## Reliance on Colors for Meaning

![inline](colors.png)

^ what it means: colors are the only way to differentiate two or more objects on the page, such as text or other symbols. color is the only thing being used to convey a meaning.

^ why it matters: it can be difficult or impossible to differentiate between these colors for people with color blindness. if the colors are not differentiable, the meaning is lost.

^ how to fix it: use symbols, patterns, or text in addition to color.

---

## Reliance on Colors for Meaning

![inline](color_good.png)

---

## Small Link targets

^ what is means: the clickable area for a link is only a few pixels large

^ why it matters: mouse users with motor control disabilities may find it difficult to target your link and successfully click on it.

^ how to fix it: either increase the size of the text/image/icon or increase the clickable area around it.

^ this also affects hover states, not just anchor tags.

---

## Difficult Fonts

![inline](arial.png)

^ what it means: fonts with difficult-to-differentiate symbols, such as “I” vs “l". this example is an uppercase-"i" and a lower-case "L"

^ why it matters: users with cognitive disabilities can have a hard time parsing these symbols, leading to confusion

^ how to fix it: select a font with symbols that are clearly differentiated.

---

## Difficult Fonts - Fixed!
![inline](dyslexie.png)

---

# And much more!
- can't skip navigation
- fonts not designed for reading on a screen
- lack of ARIA controls
- difficult-to-comprehend text
- visual-only captcha
- device dependent event handler in javascript
- missing or uninformative page title
- empty table header

---

# [fit] You can do it!

^ the web isn’t a barrier to people with disabilities, it’s a solution. the web has the potential to revolutionize the day-to-day lies of millions of people by increasing their ability to access aspects of life that most people take for granted. for the web to reach its full potential for people with disabilities, web developers must commit to always designing with accessibility in mind.

^ hopefully, i’ve given you enough knowledge to help improve the accessibility of your web sites, and i encourage you to always design with accessibility in mind. and, please, share what you have learned with others.

---

![](/Users/stephaniemarx/Desktop/SpeakerSlide/SpeakerSlide.001.png)

^ chicago code camp was brought you by these lovely sponsors

---

## Stephanie Marx
### stephaniemarx.com
### stephanie.n.marx@gmail.com

^ and that's it! i was and will continue to be stephanie marx! i'll have these slides and some additional notes, including a list of helpful tools, up on my site later today. feel free to send me an email, connect on twitter or linkedin, or check me out on github.

^ questions!

^ useful tools

^ WAVE web accessibility evaluation tool
http://wave.webaim.org/

^ WebAIM - web accessibility in mind
http://webaim.org/

^ color contrast checker: http://webaim.org/resources/contrastchecker/

^ WCAG
https://www.w3.org/TR/WCAG20/

^ the A11Y project
http://a11yproject.com/
