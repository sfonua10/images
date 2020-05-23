---
title: CSS Opinions
date: 2020-05-23
description: Css Opinions
---

It's a subjective thing. From my experience, typography is typically globally set and individually overwritten. But I also come from -> Write all your CSS by hand and use the cascade. A lot of people don't like that so they very tightly encapsulate their typography styles and everything kind of gets set by config tokens (https://css-tricks.com/what-are-design-tokens/). There's not a right way or wrong way to do this. The only thing that really matters when you're dealing with styles in an app is that the team understands which decisions have been made and agrees to enforce them the same way. So as long as everyone is on the same page, you can build a good style system for your app. Where it will start to fall apart is when there's a lot of rules you have to know, it gets tricky. I think that's where a lot of the contention in css comes in, is how much is stuff you just have to intuitively understand or stuff you have to learn through slogging through the code base, how much of the code base do you have to know to write styles, and that varies from team to team, and it's been a debate that been raging on twitter for years, so we probably won't solve that today. But my preference is to set defaults on the elements because its easy to override elements with classes or other selectors, and that way things are set here and you override them individually as you go.


Here's a trick to get a sticky footer with CSS & HTML
```
.container {
  display: flex;
  flex-direction: column;
  min-height: 100vh
}

.content {
  flex-grow: 1;
}
```

Here's the HTML
```
<div className="container">
  <div className="content">
  <Header />
    {children}
  </div>
  <Footer />
</div>

```
