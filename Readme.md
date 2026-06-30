Install local registry
```
docker run -d -p 5000:5000 --name local-registry registry:2
```

- **Usage:**
    1. **Tag your image:** `docker tag my-image localhost:5000/my-image:latest`
    2. **Push the image:** `docker push localhost:5000/my-image:latest`
    3. **To view images:** `curl -X GET http://localhost:5000/v2/_catalog`
    4. **Pull the image:** `docker pull localhost:5000/my-image:latest`
