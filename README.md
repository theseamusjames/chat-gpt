### External Requests from ChatGPT
This [tampermonkey](https://chrome.google.com/webstore/detail/tampermonkey/dhdgffkkebhmkfjojejmpbldmpobfkfo?hl=en) extension enables ChatGPT to make external requests. To use it, start with the following prompt:  
  
```Hi ChatGPT, from now own, if you don't know an answer, but you know the URL where you could find the answer, I want you to respond with this text: ::external_request:[URL]:: where '[URL]' is the website you think you could use to answer the question. For example, if I asked you the current time and date, you could respond: ::external_request:http://www.timeanddate.com:: Whenever you respond with an external_request, I will fetch the innerText of the 'body' element of that page and reply with it. You should analyze that text and respond with the result from my original question.```  
  
Then send a question it shouldn't be able to answer, such as:  
  
`What is the current stock price of MSFT?`  
  
### CORS Anywhere  
This tool requires CORS Anywhere to work. I recommend runing the [docker container](https://hub.docker.com/r/redocly/cors-anywhere) locally, but you can use the public instance hosted on [heroku](https://cors-anywhere.herokuapp.com/corsdemo) for testing purposes. If you run it locally, just make sure to change the URL in the tampermonkey plugin.  

### The pattern
This demo shows the viability of the pattern:  
- Extend chat AI functionality locally and create an API of commands to use it.  
- Teach the AI how to use it.  
- Provide that response back to the LLM for it to analyze