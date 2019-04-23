---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - python

toc_footers:
  - <a href='https://github.com/lord/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

# Introduction

Welcome to the Sike API! You can use our API to access Sike API endpoints, which will provide information on personality traits, strengths and weaknesses. 

This simple documentation page will outline how to use the API. As of now, we only have POST request functionality. This is all you will need in order to access the full suite of tools that we can offer.

The Sike API allows you to send text written by any individual, and returns a JSON object that gives you their personality traits, as well as a list of strengths and weaknesses. 

# Usage

> To use the API, send a POST request using a language of your choice in the following JSON format:

```json
{
    "text" : "Insert Text Here",
    "apiKey" : "apiKey"
}
```

> Make sure to replace <code>apiKey</code> with your API key, and <code>"Insert Text Here"</code> with over 500 words of text.

Sike uses API keys to allow access to the API. For security purposes, we will register your API key separately. Please contact us at sike.insights@gmail.com to register the key and start using the service. 

Sike expects for the API key to be included in all API requests to the server. Any requests that do not contain the API key will be rejected.

<aside class="notice">
You must replace <code>apiKey</code> with your personal API key.
</aside>

<aside class="notice">
The text must be over 500 words in length, otherwise the API will abort with an error code of 400. For optimal accuracy, we recomend sendint text that is at least 1200 words long. 
</aside>

> The above POST request returns JSON structured like this:

```json
{
    "strengths": [
        "Creative",
        "Organized",
        "Accommodating"
    ],
    "trait-values": [
        [
            "Creativity",
            81
        ],
        [
            "Organizedness",
            73
        ],
        [
            "Extraversion",
            54
        ],
        [
            "Accommodativeness",
            72
        ],
        [
        "Emotional Awareness",
        56
        ]
    ],
    "weaknesses": [
        "May have 'head in the clouds'",
        "May not work systematically",
        "May reinvent the wheel",
        "May miss some of the detail",
        "May not learn from the past",
        "May use an overly rigid approach",
    ]
}
```

This is the only endpoint currently available, and will provide a queryable list of strengths, weaknesses as well as integer values (from 0-100) of personality traits.

### HTTP Request

`POST http://saffron-api.sikeinsights.com/v1/result`

### List of Possible Strengths

Strength | 
--------- | 
Creative | 
Practical |
Organized |
Flexible |
People-Oriented |
Independent |
Accommodating |
Skeptical |
Emotionally Aware |
Calm |

<aside class="success">
Simple! You can use this list on your frontend and sort based on each strength.
</aside>

### Weaknesses

We also provide a comprehensive list of weaknesses. These can easily be accessed by parsing the JSON and looking for the value associated with the <code>weaknesses</code> key. 

### Personality Trait Values

The personality trait values are provided as a list of tuples. This list is the value of the <code>trait-values</code> key. The first element of the tuple contains the trait (one of the elements from the list below), and the second element gives an integer value (ranging from 0 to 100) of this trait.

Trait | Complementary Trait 
--------- | --------- 
Creativity | Practicality
Organizedness | Flexibility
Extraversion | Intraversion
Accommodativeness | Skepticism
Creativity | Calm
 
 > For example, an individual's creativity trait would be returned as an element of the list associated with the <code>trait-values</code> key in the JSON shown above. This element would look like this: 
 
```json
[
"Creativity",
81
]
```
