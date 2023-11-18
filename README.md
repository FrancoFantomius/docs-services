The documentation for the APIs to [services.francofantomius.com](https://services.francofantomius.com)
This is the [link](https://docs.francofantomius.com) to this documentation.

Please note that at this stage the documentation is more of a collection of examples.

## Index
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

```
{
  identification: {...},
  inputs: {
    prompt: "EXAMPLE CAT"
  }
}
```

It returns a `binary` file with the image in it.

## Speech to Text

```
{
  identification: {...},
  inputs: {
    "oneOf": [
      {
        "type": "string",
        "format": "binary"
      },
      {
        "type": "object",
        "properties": {
          "audio": {
            "type": "array",
            "items": {
              "type": "number"
            }
          }
        }
      }
    ]
    }
}
```

## Text generation

This API uses the llama 2 model to generate the response, please modify the `USER QUESTION` with the starting message

```
{
  identification: {...},
  inputs: {
    messages = [
        { role: 'system', content: 'You are a friendly assistant that is coincize but helpful and responds in the same language of the user' },
        { role: 'user', content: 'USER QUESTION' }
    ];
  }
}
```
