# Notes from the Nextcloud accessibility workshop with @jancborchardt

### axe     
        - browser extension to check acessibility https://www.deque.com/axe/
        - adds a section to dev tools
        - open source
        - used by chrome lighthouse & some other projects
        
### wave    
        - browser extension to check acessibility  https://wave.webaim.org/
        - adds button to the interface & right click "wave this page"
        - visual 

### On Mobile   
            - talk back for Android - screen reader to check acessibility
            - voice over for IOS

https://www.w3.org/TR/WCAG20/

## 1 Perceivable
    1.1 Provide text alternatives for any non-text content so that it can be changed into other forms people need, such as large print, braille, speech, symbols or simpler language.
    1.2 Provide alternatives for time-based media.
    1.3 Create content that can be presented in different ways (for example simpler layout) without losing information or structure.
    1.4 Make it easier for users to see and hear content including separating foreground from background.
## 2 Operable
    2.1 Make all functionality available from a keyboard. (keyboard only?)
    2.2 Provide users enough time to read and use content.
    2.3 Do not design content in a way that is known to cause seizures.
    2.4 Provide ways to help users navigate, find content, and determine where they are.
    Button label, 44px X 44px
## 3 Understandable (language)
    3.1 Make text content readable and understandable.
    3.2 Make Web pages appear and operate in predictable ways.
    3.3 Help users avoid and correct mistakes.
    404 pages 
    Use "link" rather than "url"
## 4 Robust
    4.1 Maximize compatibility with current and future user agents, including assistive technologies.
    Input elements using correct format on Mobile
 
### W3C validator

### Aria Labels 
https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/ARIA_Techniques/Using_the_aria-label_attribute

Screen readers also use display none
visibility none === opacity none
class="hidden-visually" : positions element absolutely and moves it off screen, it stays in the flow of the page structure (so screen readers see it) but it doesnt show
