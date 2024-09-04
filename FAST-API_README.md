FASTAPI: It is a framework for building APIs using Python.

Benefits: It supports async programming due to which it can handle large number of simultaneous requests (concurrent req) between client and server efficiently.

FastAPI is built on top of Starlette (a lightweight ASGI framework) and uses Uvicorn as the ASGI server.

Uvicorn: Default deployment server of fastapi.

Background task: Task/program can run in the backend even after sending response to client. (This has been implemented)

Background Task Implementation:
This has been implemented to prevent connection timeout error during deployment.
On api call related to "get_data": Background task is initiated and sends response to client that processing has started.
It takes approx 2 mins for completion. Steps included: Retrieve data from 3rd party api services-data manipulation-final output send to client.
After 2 mins , another api call is made which sends the output of background task to client. There are 2 error handling using HTTP exception method of fastapi
400: It indicates bad req. It happens when server is down related to 3rd party api.

Pydantic:
FastAPI uses Pydantic for data validation for get,post req and response etc.

Path & Query in FastAPI URL: 
In @app.get("/items/{item_id}").
Here item_id is a path parameter.
/items/42?q=searchterm. Here q=searchterm is a query parameter.
Body: Response to be sent or received validated using pydantic.


CorsMiddleware

APIRouter: Implemented

To define routes in separate files or modules and then include them in  main application.




