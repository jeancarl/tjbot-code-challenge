# TJBot Challenge

The following challenges demonstrate the basic capabilities the TJBot offers. Code you write using the simulator can be used on the physical TJBot.

* [Language Translator](language-translator.md)
* [Text to Speech](text-to-speech.md)
* [Tone Analyzer](tone-analyzer.md)
* [Speech to Text](speech-to-text.md)
* [Visual Recognition](visual-recognition.md)

Access the TJBot simulator at [ibm.biz/meet-tjbot](https://ibm.biz/meet-tjbot)

Please keep in mind the simulated TJBot is a simulated Node.js environment. Code is executed in the browser, except for API calls which are proxied via an IBM Bluemix application. API credentials are not stored in this proxy.

Feel free to complete more than one of these challenges, even combining them together. Here are some things to keep in mind.

* Create a new TJBot, providing an array of hardware it has: led, servo, speaker, microphone, camera
* Specify a gender, male or female, that is used by the speak method to synthsize text into a male or female voice.
* Inform the TJBot library of Watson service credentials in order for TJBot to utilize Watson.

```
var tj = new TJBot(
  ["speaker"],  // array of hardware available for TJBot to use
  { // configuration for what language to speak, etc.
    robot: {
      gender: "female"
    },
    speak: {
      language: "fr-FR"
    }
  },
  { // service credentials for the Watson services that are used
	  text_to_speech: {
	    username: process.env.TEXT_TO_SPEECH_USERNAME,
	    password: process.env.TEXT_TO_SPEECH_PASSWORD
	  }
	}
);

// use the methods available from the TJBot object.
tj.speak("bonjour");
```

Check the Docs tab for sample code demonstrating some of the capabilities TJBot has to offer.
