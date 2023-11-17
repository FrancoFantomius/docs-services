# Francofantomius Services | Documentation
The documentation for the APIs to [services.francofantomius.com](https://services.francofantomius.com)

1. [Introduction](#introduction)
1. [Translation APIs](#translation-apis)
2. [Image Generation](#image-generation)
3. [Speech to Text](speech-to-text)
4. [Text generation (LLMs)](text-generation)

## Introduction

The standard format for accessing this APIs is:
```
{ 
  identification: { key: 'KEY', password: 'PASSWORD' }, 
  inputs : {...} 
}
```
**NOTE**: For using this APIs you need a KEY and a PASSWORD to access the identification services, otherwise the request will not be processed. 

## Translation APIs
Example of a request:

```
{
  identification: {...},
  inputs: { 
    text: "Hello world!",
    source_lang: "english",
    target_lang: "french"
    }
}
```
The `source_lang` defaults to english.
The supported languages are english, chinese, french, spanish, arabic, russian, german, japanese, portuguese and hindi.

## Image Generation



## Speech to Text

## Text generation
