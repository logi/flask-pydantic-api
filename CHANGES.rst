1.7.0
-----

Released 2025-06-02

- Fix how union types are serialized in responses when specified with | shorthand.  @mtblanton
  https://github.com/adamsussman/flask-pydantic-api/pull/11
- Add support for Flask type specification in Flask route paths. @logi
  https://github.com/adamsussman/flask-pydantic-api/pull/12
- Support description in decorator and defaults from view_func @logi
  https://github.com/adamsussman/flask-pydantic-api/pull/13



1.6.0
-----

Released 2024-04-24 

- Minimum supported python version is now 3.10
- Fix issues rendering sample rapidoc template
- Fix optional enhanced serializer import handling, especially when not installed.  @mikep-wmt
  https://github.com/adamsussman/flask-pydantic-api/pull/9
- fix(serializer): fix multiple errors ocurring without the serializer extra. @noirbizarre
  https://github.com/adamsussman/flask-pydantic-api/pull/8
- Change return-type of annotated endpoint to Response @logi
  https://github.com/adamsussman/flask-pydantic-api/pull/6


1.5.0
-----

Release 2025-01-05

- Handle more cases of asyncio shenanigans
- Handle rare case of nested inner api calls with nested expansions that require a different event_loop and require
  forwarding Flask app and request contexts.
- Added better error handling and response when json body requests are not dictionaries.


Version 1.4.0
-------------

Released 2024-12-10

- Fix https://github.com/adamsussman/flask-pydantic-api/issues/4: Correctly handle GET with json Content Type and
  empy request body.
- Replace method of getting apidocs template path that accounts for pkg_resources being removed in Python 3.12


Version 1.3.1
-------------

Released 2024-09-06

- Fix https://github.com/adamsussman/flask-pydantic-api/issues/2: Correct Content-Type header when not using
  pydantic_enhanced_serializer

Version 1.3.0
-------------

Released 2024-09-06

- Add @pydantic_api parameter `get_request_model_from_query_string`.  This instructs the OpenAPI schema generator
  to put the request model's parameters into the query string specification.


Version 1.2.0
-------------

Released 2024-06-09

- Add pydantic_api parameter `success_status_code_by_response_model`.  This allows methods that specify a return
  type that is a Union of multiple BaseModels to also specify a specific http status code depending on which
  model is in the actual response.
- OpenAPI schemas will now correctly reflect cases where the response is a Union of multiple pydantic models including
  custom statuses per model.
- Allow method request body type to be a Union of a model with a file upload and another non-upload model


Version 1.1.0
-------------

Released 2023-12-01

- Removed openapi-pydantic as a methodology and moved to pure native python data structures
  (dicts, etc) for OpenAPI.
- Many reworks and fixes to how openapi schema is generated.


Version 1.0.0
-------------

Released 2023-11-27

BREAKING CHANGES

- Conversion to Pydantic 2.0.  Pydantic < 2.5 no longer supported.
- Added `model_dump_kwargs` argument to `@pydantic_api`


Version 0.10.0
--------------

Released 2023-10-12

- Added ability to get at the `fields` request value by adding a field: List[str] argument
  to the @pydantic_api wrapped work function.


Version 0.9.7 - recalled
Version 0.9.6 - recalled

Version 0.9.5
-------------

Released 2023-05-30

- Improve scope of catching pydantic validation errors when creating response models inside wrapper
  handlers and unintentionally showing those errors to API callers.


Version 0.9.4
-------------

Released 2023-05-17

- Add support for extra openapi schema data in @pydantic_api argument


Version 0.9.3
-------------

Released 2023-04-13

- Add support for file uploads via multipart/form-data in models and openapi schema

- Add `fields` parameter to openapi query strings and request bodies if response models
  have fieldsets defined.


Version 0.9.2
-------------

Released 2023-04-01

- Pass any kwargs for `get_openapi_schema` into `OpenAPI.parse_obj`.


Version 0.9.1
-------------

Released 2023-03-28

- Fix broken OpenAPI schemas for empty responses.


Version 0.9.0
-------------

Released 2023-03-18

- Initial public release.
