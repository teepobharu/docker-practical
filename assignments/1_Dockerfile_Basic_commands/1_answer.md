Executing Container
- Require to interact with python input
- Expose to right port on server 3000

```
# Python
docker run -it python-image
docker start -i -a python-image

# Node
docker run -p 3000:3000 --rm node-image

```

Remove Images
```
dokcer image prune -a
```