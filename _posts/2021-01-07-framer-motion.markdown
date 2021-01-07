---
layout: post
title:      "FRAMER-MOTION"
date:       2021-01-07 13:34:12 -0500
permalink:  framer-motion
---

According to the documentation, Framer is a design and prototyping tool. They offer an API for using Framer components and features, as well as a smaller API called Motion, which is an animation and gesture library. Framer and framer-motion are built to work with React, and can give otherwise static components a very polished and dynamic feel.

Framer-motion is lightweight and very easy to implement, all you have to do is:

	
	npm framer-motion install
	

then insert the following into the React component you'd like to use it in:

	import { motion } from ‘framer-motion’

## **MOTION**
---
### *ANIMATIONS*
To illustrate how to use the API, let's look at a simple example, like adding some animation to a button when hovering over it.

First, we need to start by adding 'motion.' to the beginning of the relevant html tag, in this case it would look like:

```js
<motion.button>Click Me!</motion.button>
```

We can then use the **animate** prop and Motion will generate the animation for us when the component is rendered to the DOM. In this example we'll increase the size of the button.

```js
<motion.button animate={{ scale: 1.1 }}>
    Click Me!
</motion.button>
```

The **transition** prop can be used to override and control animations. The following could be included just after **animate** make the transition take two seconds, and to delay the animation start by two seconds.


`transition={{ delay: 2, duration: 2 }}`

### *GESTURES*
Props relating to hovering, tapping, panning, and dragging of components are also a part of the Motion API. Adding some gesture control to the previous example, the code below would render the button after a delay of two seconds, then take two seconds for the scale animation. 

```js
<motion.button
    animate={{ scale: 1.1 }}
    whileHover={{ opacity: 0.5}}
    whileTap={{ opacity: 1 }}
    transition={{ delay: 2, duration: 2}}
>
    Click Me!
</motion.button>
```
Now, if the user hovered over the button, there would be a two second delay, and then the opacity would be reduced to .5 over the next two seconds, with the opposite series of events happening when the user is no longer hovering over the button. While hovering over the button with the animation played through and opacity set to 0.5, if the user taps the button...nothing happens. You might expect there to be a delay of two seconds and then opacity set to 1, but for that we'd need to use the onTap prop. Using whileTap, the user must keep the button pressed in order to activate the animation. There are multiple props for the different gesture types, which provide for some pretty granular control over the user experience.

### *VARIANTS*
Variants allow for animations that propogate through the DOM instead of just targeting one component. This is extremely useful if a component has children, because the changes propogate downward through the children unless a child component defines its own **animate** prop. This example was pulled from the documentation, but it illustrates the concept pretty well.

```js
const list = {
    visible: { 
        opacity: 1 
     },
    hidden: {
       opacity: 0
    }
} 

const item = {
    visible: {
        opacity: 1,
        x: 0
    },
    hidden: {
        opacity: 0,
        x: -100
    }
}

return (
     <motion.ul
         initial='hidden'
         animate='visible'
         variants={list}
     >
         <motion.li variants={item} />
         <motion.li variants={item} />
         <motion.li variants={item} />
     </motion.ul>
)
```

The default setting runs the animations at the same time, but using variants unlocks additional props like **when**, **delayChildren**, and **staggerChildren**, providing control over when the related animations occur.

In this example, the list animates before its children, and each child animation is staggered by 0.3 seconds, and when the hidden variant is used the list will change its opacity only after its children have already done so.

```js
    const list = {
        visible: {
            opacity: 1,
            transition: {
                when: 'beforeChildren',
                staggerChildren: 0.3
            }
        },
        hidden: {
            opacity: 0,
            transition: {
                when: 'afterChildren'
            }
        }
    }
```


## OTHER FEATURES
The things listed here are just a small piece of what is possible using the Motion API. Some of the other interesting possibilities include controlling transitions with **keyframes**, changing the stiffness/springiness/inertia of animations, setting animations for when components are unmounted from the DOM, plus a lot more. I found it really easy to implement and experiment with, and it looks amazing. If you're curious and want to look over the documentation and see some examples in action, you can [check it out here](https://www.framer.com/api/motion).
