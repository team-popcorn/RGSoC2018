# Notes from meeting with App Maintainer
##### *28.08.2018*

### Dates
    - Friday 21st September 16:00 - release the Beta 1
    - 22nd - 29th September - Bart away
    - Early October - release the Beta 2
    - 28th September - end of RGSoC

### Dav lib 
    - network connection
    - add to server.then(add to local state)
    
### UI is pretty close

### Communication of issues on github page
    - Create issues after Arati merges today
    - labels for issues Beta-feedback & vue

### Other points
    - Comments more on PRs than on individual commits
    - PR - change Addressbook & AddressBook to match just need to decide which way
    - kebab case or camel case for css sheets
    
#### Testing
    - Unit tests (for every function)
    - Vcard tests (invalid vs valid, testing all actions)
    - Integration tests (emulate user using the app)
    - We will a date for a screen sharing session to show an example of testing
    
### Notes on getting contacts
    - using array to use javascript references array[uid] or array.find(value => value == value) 
    - Objects however were faster than using an array
    - Sorting with Objects is more difficult as there is no orders only keys
    - Sorting previous with array was very computational expensive as it had to go through every object.
    - Now we can take the keys and put them in an array and first sort this and then apply the order to the 
    - Every time you click a contact a new version is created in the details section which exists in the virtual dom and is only sumbitted to the server when the contact has been changed (Reactivity). This function is called updateContact in our app and there is a debounce of 50ms attached to delay when the mutations are called.
    - ical.js passes Vcards and matches version of Vcard If a property that is not valid in that version the property will be set to unknown. These properties will be ignore & not appear in our app.
    ###### contactDetailsPropert.vue
        - v-if checks is property type == unknown and doesnt show it
        - A dynamic component is made and given a property type
        - The component is blank and the type is set with is:componentInstance
    - check rfc standars
    ###### .sync 
        - we can have .sync value on a property such as selectType.sync
        - where we have this.$emit(update:variableName, this.localValue)
        - With this :variableName.sync="value" values will be updated when the emit runs the event and the value is updated. Only effective for direct parents.
    ##### watcher
        - fallback to make sure that if you change a contact locally in one addressbook and then you go to the same contact in a different addressbook it makes sure you see the updated data
        - update of selectType (Home/ Work/ Fax)


### Plugin better comments //!
* ? highlighted in blue
* ! highlighted in red
* TODO highlighted in yellow

### Plugin Document this
can do /* above function and click document this to create comment for the function
    
