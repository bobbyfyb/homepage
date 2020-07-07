---
description: >-
  two problems met when developing with bing web search api of azure cognitive
  service and slack app api, and their solution.
---

# slack chatbot with bing web search of azure cognitive service developing tips

## Bing web search api python SDK

### problem description

if trying runing the instance program of official document [https://docs.microsoft.com/zh-cn/azure/cognitive-services/bing-web-search/quickstarts/client-libraries?pivots=programming-language-python](https://docs.microsoft.com/zh-cn/azure/cognitive-services/bing-web-search/quickstarts/client-libraries?pivots=programming-language-python),  you will receive an error of "resourse not found".

### solution

in the official document it says to  Replace `YOUR_ENDPOINT` with your endpoint url in portal, while actually the python SDK will automatically complement the endpoint url from "/bing...", so you should just set endpoint to the prior part. for example, for the endpoint [https://api.cognitive.microsoft.com/bing/v7.0/search](https://api.cognitive.microsoft.com/bing/v7.0/search), just use https://api.cognitive.microsoft.com. The SDK will automatically add "/bing/v7.0/search".



## slack app

### problem description

When constructing chatbot which will response to user's input, the chatbot calls the event adapter infinitely and won't stop posting message unless manually terminate the server.

### solution

this problem arises because the chatbot reacts to message posted by itself and will stuck in the loop of reacting to itself. To solve the problem, explicitly check the user\_id of the message when an event comes and react only to the message post by the user\_id of the real user.







