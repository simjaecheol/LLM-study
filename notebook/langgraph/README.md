# Langgraph

### HumanMessage

| name | type | description |
| --- | --- | --- |
| content | str | user query |
| additional_kwargs | dict | additonal arguments |
| response_metadata | dict | metadata for response |
| id | str | unique id |

### AIMessage

| name | type | description |
| --- | --- | --- |
| content | str | ai response |
| additional_kwargs | dict | additonal arguments |
| response_metadata | dict | metadata for response |
| id | str | unique id |


- additional_kwargs `dict`
  - tool_calls `List[dict]`
    - id `str`: tool_calls id
    - function `dict`
      - arguments `dict`
        - query
      - name `str`: tool name
    - type `str`
  - refusal: `None`
- response_meta_data `dict`
  - token_usage `dict`
    - completion_tokens `int`
    - prompt_tokens `int`
    - total_tokens `int`
    - completion_details `dict`
      - reasoning_token `int`
      - audio_tokens `int`
      - accepted_prediction_tokens `int`
      - rejcted_prediction_tokens `int`
    - prompt_tokens_details `dict`:
      - cached_tokens `int`
      - audio_tokens `int`
  - model_name `str`
  - system_fingerprint `str`
  - finish_reason `str`: 'tool_calls'
  - logprobs: `None`
- tool_calls `List[dict]`
  - name `str`
  - args `str`
  - id `str`
  - type `str`
- usage_metadata `dict`
  - input_tokens `int`
  - output_tokens `int`
  - totak_tokens `int`
  
### ToolMessage
| name | type | description |
| --- | --- | --- |
| content | `List(dict)` | tool response |
| name | `str` | tool name |
| id | `str` | unique id |
| tool_call_id | `str` |  |
| artifact | `dict(Optional)` | search results |
| response_time | `float(Optional)` | search response time |

- content `List(dict)`
  - url `str`
  - content `str`
- artifact `dict`
  - query
  - follow_up_questions
  - answer
  - images
  - results `List(dict)`
    - title `str`
    - url: `str`
    - content `str`
    - score `float`
    - raw_content: None

## Tutorial

## Multi Agents Collaboration