
# What is RESTForms2?
Is an community package that allows you to automatically create REST API backend for InterSystems IRIS persistent classes / tables.

You can find more information in:
* [restforms2](https://openexchange.intersystems.com/package/RESTForms2)
* [RESTForms - REST API for your classes](https://community.intersystems.com/post/restforms-rest-api-your-classes)
* [RESTForms - REST API for your classes. Part 2: Queries](https://community.intersystems.com/post/restforms-rest-api-your-classes-part-2-queries)


# Installation

Open a session to connect to IRIS

```
docker exec -it iris bash
iris session iris
```

Install [InterSystems Package Manager (IPM)](https://openexchange.intersystems.com/package/InterSystems-Package-Manager-1)

```objectscript
// install zpm
set r=##class(%Net.HttpRequest).%New(),r.Server="pm.community.intersystems.com",r.SSLConfiguration="ISC.FeatureTracker.SSL.Config" d r.Get("/packages/zpm/latest/installer"),$system.OBJ.LoadStream(r.HttpResponse.Data,"c")
```

Install [restforms2](https://openexchange.intersystems.com/package/RESTForms2) using InterSystems Package Manager.

```objectscript
zpm "install restforms2"
```

# Test it!

Populate sample data

```objectscript
do ##class(Form.Util.Init).populateTestForms()
```

Try **RESTForms.postman_collection.json** Postman collection to test some methods.

# Some more examples
Have a look at a full application built using restforms2 apis, check [iris-datapipe](https://openexchange.intersystems.com/package/iris-datapipe)