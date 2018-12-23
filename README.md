Source code for my personal website
------------
I'm using the [Poole Theme](http://getpoole.com/) and [Jekyll](https://jekyllrb.com/)

I've made some changes to the original theme mainly around the top masthead
by changing the background color and adding a `<hr>` to split out the links from the smaller tag line.


In `_sass/_masterhead.scss`:
```
.masthead-hr {
  position: relative;
  margin: 0.25rem 0;
  border: 0;
  border-top: 1px solid #B77700;
  border-bottom: 1px solid #FFC964;
}
```


### Setup instructions

Simple setup based on the instructions: https://jekyllrb.com/docs/

Didn't bother to install `bundler` since I'm not really using Ruby Gems for
various projects (just this one)

Serve up using:

```bash
jekyll serve
```
