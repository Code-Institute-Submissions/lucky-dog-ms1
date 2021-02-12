# Lucky Dog - Testing details

[Back to README.md file](README.md)

[Live Website](https://mosull20.github.io/lucky-dog-ms1/)

### Code Validation

1. HTML Validated on [W3C Markup Validation Service](https://validator.w3.org/)
    * Home page - 1 error ![Error image](testing-images/home-page-error.png)
    - Solution found via W3 schools - syntax changed to "image/png". After this amendment, code was run through again and passed with no errors.
    * Services page - no errors found 
    * Team page - no errors found
    * Contact page - 7 errors found ![Error image](testing-images/contact-errors-1.png) ![Error image](testing-images/contact-errors-2.png)
    - Solution - error 1 - adjusted the width to replace the % value that was there.
    - Solution - error 2 - deleted frameborder attribute as this is now obsolete, researched this on google, included `border: none;` in css as recommended.
    - Solution - errors 3,4,5,6 - found on Slack community, this text can now be removed as iframes are now supported on all browsers,
    and instead a "title" attribute is used which I then added. I double checked this for myself on [Can I Use.com](https://caniuse.com/?search=iframe)
    and followed a link from there to [MDN Webdocs](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe#browser_compatibility).
    - Solution - error 7 - changed the aria-describedby value to "name" to link it to the id name.
    - After implementing these solutions, I ran the code through the validator again and it passed with no further errors.

2. CSS Validated on [Jigsaw W3C CSS Validation Service](https://jigsaw.w3.org/css-validator/) 
    * Passed with no errors found ![Error image](testing-images/css-no-errors.png)
    * Two warnings were found ![Warning image](testing-images/css-warnings.png)
    * Solution - no action required on first warning as the @import content cannot be checked. Re the second warning, I removed border-color style rule from style.css 
    as it was unnecessary.

    * NOTE: the above was done before running my css file through the autoprefixer resource. After, I ran it again through the Validator and got the following warnings. 
    ![Error image](testing-images/css-autoprefixer-warnings.png)
    * After checking this on the Slack community, I understand these warnings do not require action.


### Manual Testing

#### Lighthouse testing

* Tested each page at mobile size and desktop size and got the following results

+ Home page - mobile

![Lighthouse image](testing-images/home-mobile.png)

+ Home page - desktop

![Lighthouse image](testing-images/home-desktop.png)

+ Services page - mobile

![Lighthouse image](testing-images/services-mobile.png)

+ Services page - desktop

![Lighthouse image](testing-images/services-desktop.png)

+ Team page - mobile

![Lighthouse image](testing-images/team-mobile.png)

+ Team page - desktop

![Lighthouse image](testing-images/team-desktop.png)

+ Contact page - mobile

![Lighthouse image](testing-images/contact-mobile.png)

+ Contact page - desktop

![Lighthouse image](testing-images/contact-desktop.png)

___

#### Functionality testing

I used [Google Chrome DevTools](https://developers.google.com/web/tools/chrome-devtools) continuously throughout the project to check how every detail worked, 
particularly with regard to checking responsiveness of each feature as I worked on them. 

Here are the steps taken in testing the website is now functional.

**__Home page__**
+ Nav Bar: 
  - clicked on paw print logo - re-loads the home page
  - clicked on Home link at right hand side - reloads home page
  - clicked on Our Services link - brings user to services.html page
  - clicked on Meet the Team link - brings user to team.html page
  - clicked on Contact Us link - brings user to contact.html page
  - checked the nav menu links collapse into hamburger icon at mobile level and when selected it drops down the links menu
  - Scroll down to visually check the Nav Bar is sticky and remains visible at top of page while scrolling down

+ Content section:
  - clicked on link at end of first paragraph - brings user to team.html page as expected
  - clicked on Get in Touch link in second paragraph - brings user to contact page as expected
  - clicked on Contact us link in third paragraph - brings user to contact page as expected
  - read through all content again to check for typo's or any other content errors. Two found at this stage and I corrected them. 
  - checked overall responsiveness by using Chrome dev tools to view it on mobile and tablet size devices
  - checked images for responsiveness and ensure they hold a good relative, proportional size at each screen size and do not get squashed 
or stretched when at different screen sizes.

+ Footer section:
  - clicked on Get in Touch link - brings user to contact page as expected
  - clicked on each social media link to ensure it brings the user to social media pages that open in a new browser window, all performed as expected

**__Services page__**
+ Repeated all the above steps re the Nav Bar and Footer to ensure those links all work as expected on this page
+ Content section:
  - clicked on each of the four contact buttons to ensure they each linked correctly - all bring the user to the contact page
  - checked responsiveness of the page overall on each screen size in DevTools
  - checked responsiveness of images within each box to ensure they retained their original proportion at each screen size and performed as expected

**__Team page__**
+ Repeated all steps above re Nav Bar and Footer, to ensure all links work from this page. Found the Get in Touch link in the footer did not lead 
the user to the contact page as I had not replaced the placeholder for the href attribute so I corrected this. 
+ Content section 
  - clicked on contact us button - brings user to the contact page
  - checked all image and text at various screen sizes to ensure all in proportion 

**__Contact page__**
+ Repeated all steps above re Nav Bar and Footer to ensure all links work. All work correctly.

+ Contact form: 
  - clicked send it button with no input anywere in the form, it ask user to fill in name field, tried again with no email input, 
form correctly rejects it and prompts user to enter email. Phone number field is optional so it will send with this blank, This is intentional. 
Tried sending with no input in message area and it will correctly prompt user to fill in this field. Once all complete, action of send it will open 
the CI form dump page in a new broswer window, as intended.
+ Embedded google map: 
  - works as expected, with the google maps buttons contained opening a larger map in a new broswer window, or enlarging the map in its container.

____

#### Responsiveness

* Checked the project's responsiveness at [Responsinator.com](http://www.responsinator.com/)

#### Cross Browser Testing

I checked the website on the following broswers - Chrome, Firefox, Safari, Opera and Microsoft Edge and all displayed and functioned as intended. 

___

### User stories Testing

___

### Bugs & Fixes

* Wireframe issues - problems linking to wireframes from this file so I moved the wireframes folder from assets to root level, re-exported the original wireframes from Balsamiq 
and re-loaded to the wireframes folder. Content of wireframes not changed from original during this process. 

* On initial Lighthouse testing, SEO was reading at 81, one opportunity it highlighted to improve this was to add metadata tags.
I then added the meta tage with description, keywords and author. This improved the SEO to the above result.
Lighthouse also gave me the opportunity to spot that I had not gone in sequential order with my h tags so I amended this and it also
helped to improve the accessibilty from an initial reading of 88.

