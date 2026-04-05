# Pop-out Tags

**For:** Projects Showcase on my Portfolio Site

Basically, when someone hovers over a div for a project, some extra details about the project should show up. 

On hover, a project card reveals additional details via animated "pop-out" tags. These tags fly outward from the card, snap into place, and idle with a subtle breathing animation. On mouse-leave, the animation reverses.


![Sketch of the default and active state of the div](visual/Pop-out-Hover-Tags-Sketch.PNG)

| *Figure: Sketch of the default and active state of the Pop-out div*

## Structure:

### Card (`.project-card`)

*The main div containing everything*

- Dynamic sizing or fixed sizing? TBD

Background
- An image taking up the full width/height

Text
- A headline/Title text
    - The title of the project
- A short subtitle text 
    - a short paragraph describing the project
- Aligned to the bottom of the div

---

### Tags

Absolute positioning for each and every "tag" item.

Each tag is absolutely positioned relative to the card. Placement is manually curated per card - a helper function can be used to suggest aesthetic starting positions, but final placement should feel intentional and visually balanced.

Each tag is:
- An **icon** (e.g. a tech logo, tool, or category symbol)
- A **text label** 

Tags can vary. Some may be icon + text paired together but the default is icon-only or label-only


---

### Animation

*Pop out tags.*

### On hover - tags pop out

Tags originate near the center of the card and animate outward to their final positions. The motion overshoots slightly before snapping into place (spring/elastic easing).

- Origin: ~50px inward from each tag's final destination
- Easing: overshoot → snap (e.g. `cubic-bezier` or spring physics)
- Entry includes sparkle/star particle effects

### On idle - tags breathe

Once settled, tags float gently up and down in a slow, looping animation.

Created a wrapper around each tag so that the tags have their previously created pop-out animation, and then the wrapper element is the one that has the breathing idle animation. 

The wrapper floats, the inner tag snaps in; two separate transform contexts, no conflict.

### On mouse-leave - reverse

Tags animate back toward the center and fade out, reversing the entry sequence.


---

## CSS implementation

The default currently is the final view. Visible and spread out. 

The default should be invisible and closer to the center. Additionally, I need to have a transition **behavior...?** What I mean is there needs to be a smooth transition (opacity and positioning). Do I use translateX/Y or just the top/bottom/left/right properties that absolute position uses? 

...AI did it for it me.

## How to use

- Copy and paste the SECTION to the html file where you plan to use this.

- Copy the CSS file to wherever your css files lie (e.g. relative folder "./css/")

- ADD this to <head> "<link rel="stylesheet" type="text/css" href="./css/Pop-out-Hover-Tags.css" />" 

- Edit the "background-image: url('....')" in-line style for each project card

- Add href link page 

- Edit the individual tag text


# Later Ideas

- Shrink the other cards - non-hovered cards - to make the tags more legible and not over lap with the other cards' content