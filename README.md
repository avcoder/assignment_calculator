# Assignment Calculator
My Assignment Calculator http://codepen.io/avcoder/full/PbZGZq/ uses Vue.js and tachyons.io (css framework) to help students enter a due date for a particular kind of assignment, and the program outputs a set of milestone dates from which students can work towards finishing their assignment.

## Motivation
Our library's website uses a content management system by Springshare's LibGuides.  Consequently, as a programmer, I'm limited to only creating/editing html/css/js (i.e. client-side code).  Fortunately, the javascript framework Vue.js allowed me to create this single page application without direct server-side coding access to a webserver.

## Getting Started
Fork my code on http://codepen.io/avcoder/pen/PbZGZq  or clone this git repository.  However, my git repository is only one file which already combined my html/css/js code.  Also keep in mind, that since I used HTML5's date input field, certain browsers other than Chrome may not work properly.  I could not find a satisfactory datepicker solution that was keyboard navigable (for WCAG  accessibility requirements).

### Prerequisites
The HTML file contains one template per assignment-type.  If you wish to eliminate or add steps, you would do so by creating/deleting a steps component.
```
  <template v-if="picked === 'essay'">
    <template v-if="isDatesPicked()">
      ...
      <steps v-bind:stepobject='ressay1'></steps>
      <steps v-bind:stepobject='ressay2'></steps>
      <steps v-bind:stepobject='ressay3'></steps>
      <steps v-bind:stepobject='ressay4'></steps>
      <steps v-bind:stepobject='ressay5'></steps>
      <steps v-bind:stepobject='ressay6'></steps>
      <steps v-bind:stepobject='ressay7'></steps>
      <steps v-bind:stepobject='ressay8'></steps>
      <steps v-bind:stepobject='ressay9'></steps>
      <a class="f6 link dim br-pill ba ph3 pv2 mb2 dib light-purple" href="#top">Back to top ^</a>            
    </template>
  </template>
```

Each step is defined by one variable object which can be edited to suit your own educational goals.  It contains room for only one link which will look like a call to action button at the bottom of the card set.  For example, note how the first steps component listed uses 'ressay1' which is defined in the javascript below.

```
var ressay1 = {
      step: '1',
      heading: 'Clearly state your research question',
      todos: {  
          1: 'Review the guidelines and if you need further clarification, check with your professor',
          2: 'General Definition: A research essay is a piece of writing that provides information about ...
          3: 'For help developing your research question view "Taming Your Research Topic"'
      },
      linkURL: 'https://www.youtube.com/watch?v=lrT4U8Nq9OQ',
      linkText: 'View video: Taming Your Research Topic',
      percentage: '10' // percentage of time needed to complete this milestone.
};
```

### Built with
* [Vue.js](https://vuejs.org/) - The javascript framework used
* [tachyons.io](http://tachyons.io/) - The CSS framework used

## Deployment
I simply combined my html/css/js code found on my codepen and pasted it into an HTML5 boilerplate template within the body tags, I included Vue.js' CDN link in the script tag, and similarly included tachyons' link within the head tag. Upon saving it as an html file, I uploaded it into LibGuides as an asset.  The resulting id number given was then appended to our library URL.  For example, if your id number was 26667161, then the link to run the application would be  http://[Your library website]/ld.php?content_id=26667161

## Acknowledgments
* As a guide, I used the functionality/output of what I saw from Research Project Calculator https://rpc.elm4you.org/
* and Humber College's Assignment Calculator http://www.humber.ca/assignment-calculator/
