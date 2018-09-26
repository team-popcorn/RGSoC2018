# :computer: Testing with [Markus](https://github.com/axlwaii)

##### ✅ is important
##### ✅ gives you an idea of your code
##### ✅ ideas for improvements
##### ✅ show where you may have unnesscary code

🗣️ *“Not build functions around what we need and not what the function should do.”*

example:

`
  //BAD function sum(a, b) {return 2}
`

Behaviour driven test frameworks (jasmine, jest, mocha, etc)

Assert functions - tests if a case is true or false

`
function assert(name, condition) {
	console.log(`${name}: ${condition}`)
	return condition
}
`

- name - what we are testing
- condition - we are testing

*example:*

		assert(‘Sum 1+1 should be true’, sum(1,1) === 2);

- Nested functions in tests allow us to make tests more descriptive.

- Most frameworks have built in functions that can be chained.

*example:*

		expect(a).toBeANumber(); //matcher function 
		expect(a).toBe(true);
		expect(false).not.toBe(true);
    
    beforeEach(() => {
      service = myService;
    }

*example of test framework ([Jasmine](https://jasmine.github.io/)):*

	describe("A suite is just a function", function() {
		var a;

 		 it("and so is a spec", function() {
    			a = true;

   			 expect(a).toBe(true);
  		});
	});


- Describe block - describes test
- It - States what it should do
- Expect - actually tests the outcome - returns true or false

*** Watch out for the scope of values!! ***

Test frameworks should do the work for you and make development fun!

## Code coverage ([Instabul](https://istanbul.js.org/))

100% - every line of code is tested, but doesnt ensure there are no :bug:s

Shows coverage and takes you to lines that aren't covered by tests.

##### pending()
- test needs to still be taken of, so the test case is indentified
