# Pythian - DevOps Consultant Challenge

## Overview

At Pythian, our DevOps Consultants must have a wide depth of knowledge across several key technologies.  The team expects that its members will be curious and constantly learning.  We do this to improve our skills so that we can deliver value to our clients, and be thought leaders within their organizations, as well as within Pythian.

Part of our interview process for prospective candidates is this technical challenge.  It exists to give you an opportunity to show off your skillset.  It also allows us to see how you approach a new problem, and the type of solution that you create.

You can expect to spend 1-3 hours on this challenge.

## What you'll be building

For this challenge you'll be building a set of Docker images that run a simple REST API and a persistent data backend (the data backend doesn't need to store data beyond the life of the container).

In the first container, implement a simple REST API using the language and toolset of your choice (Python, Node.js, etc...).  The REST API should support GET requests on two endpoints

    * /cat
    * /history
    
### /cat endpoint

The `/cat` endpoint should return a JSON object representing an image from the [Cat API](http://thecatapi.com/docs.html).  When a GET request is made to your `/cat` endpoint, your API backend should query the Cat API for a new image and return the details in the following JSON format.

```
{
  "image": {
    "url": "http://24.media.tumblr.com/tumblr_m3ay3e1zHp1qcxyrro1_1280.jpg",
    "id": "c11",
    "source_url": "http://thecatapi.com/?id=c11"
  }
}
```

Additionally, the details of the returned cat image should be stored so that it can be later recalled by the `/history` endpoint.  The storage backend should be a database or key/value storage platform like Redis.  The storage solution should be running in a separate container than the REST API.

### /history endpoint

The `/history` endpoint should return a JSON object representing all of the previously queried images from the Cat API.  Your software should read from your persistent storage container and return a list of cat images in the following format.

```
{
  "images": [
    {
      "url": "http://24.media.tumblr.com/tumblr_m3ay3e1zhp1qcxyrro1_1280.jpg",
      "id": "c11",
      "source_url": "http://thecatapi.com/?id=c11"
    },
    {
      "url": "http://thecatapi.com/?id=65s",
      "id": "65s",
      "source_url": "http://24.media.tumblr.com/tumblr_luu4l5amkp1qzxrnuo1_1280.jpg"
    }
  ]
}
```

The idea here is that we can run your images in Docker (hopefully using docker-compose) and then hit your `/cat` and `/history` endpoints using a simple tool like curl or Postman.

### Configuration

Please don't include any usernames, passwords, or API keys in your solution.  Instead, provide a way for us to provide those details when we launch containers from your images.  Relevant documentation should be provided.

Please include as many parameters as you'd like, but be sure to at least require that a Cat API key be passed in when launching an API container.

### Other Thoughts

Because this is an opportunity to show off your skills, it's better to use a basic Docker image that you then configure yourself.  For example, it might be easier to use a container that has MySQL pre-installed.  This would normally be a fine way to proceed, but in this case, it doesn't give you the opportunity to show that you know how to automatically install and configure a database.  Keep this in mind when building your Docker images.

## Review Guidelines

We evaluate challenge responses using the following criteria

  * Does the solution work?
  * Is the code consistently styled?
  * Is the code easy to read and understand when reviewed by an experienced DevOps team member?
  * Is the entire solution representative of the quality of work that would be expected from a member of our DevOps team?  Examples of this include
    * Use of parameters instead of hard-coded values, where appropriate.
    * Error handling.
    * Helpful documentation.
    * Use of popular libraries (modules, recipes, plugins, etc...), where appropriate.

## Solution Submission

We prefer that final solutions be delivered via a public GitHub repository.  Please note that due to the nature of public GitHub repositories, your solution will be publicly available for as long as you keep the repository.

Other arrangements can be made for circumstances in which candidates are not comfortable releasing their code via a publicly accessible repository.  Please let us know if you would prefer an alternate method of sending your solution.  It's preferred that the version control history be maintained so that it may be reviewed.
