# Language Translator

TJBot can translate content with the help of the [Watson Language Translator Service](https://ibm.biz/catalog-language-translator).

## Create a Watson Language Translator service

1. Sign up for an IBM Bluemix account at [bluemix.net](https://bluemix.net). If you already have an IBM Bluemix account, sign in.

2. Click on the __Catalog__ link in the top right corner of the Bluemix dashboard.

3. Select the __Language Translator__ service tile under the __Watson__ section of the catalog.

	![](assets/catalog-lt.png)
	
4. Click on __Create__ to create a service instance.	
5. Select __Service Credentials__ in the left sidebar.

	![](assets/sidebar-lt.png)
	
6. Click on __View Credentials__ to display the credentials. Copy the username and password credentials into the `.env` file in the simulator.

	![](assets/servicecredentials-lt.png)
	
```
LANGUAGE_TRANSLATOR_USERNAME=
LANGUAGE_TRANSLATOR_PASSWORD=
```

## Command TJBot to Translate Content

For each step, REPLACE the placeholders `/* step ## */` with the suggested code. Do not keep any part of these placeholders in the final code! 

1. First, we create a TJBot object. Here's a template to start with. Copy the template into the `app.js` file in the simulator. 

	```
	var tj = new TJBot([], {}, {
	  /* step #2 */
	});
	
	/* step #3 */
	```
		
1. Configure the Watson Language Translator credentials TJBot should use to listen. Earlier we stored them into an environment variable. 

	```
	  language_translator: {
	    username: process.env.LANGUAGE_TRANSLATOR_USERNAME,
	    password: process.env.LANGUAGE_TRANSLATOR_PASSWORD
	  }
	```
	
1. We now have a TJBot configured to translate content. Call the `translate` method with the content and source and destination language codes. When TJBot translates the text, a callback function will be passed the text TJBot translated. 

	```
	tj.translate("Hello", "en", "fr")
	  .then((response) => {
	  	console.log(response.translations[0].translation)
	  });
	```
	
1. Run the code by clicking on the play icon. Did TJBot translate the content and output the text into the console? You've completed this challenge.