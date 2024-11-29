# Amazon Web Services

It let's you

1. Rent Servers
2. Create Servers
3. Manage domains
4. Upload Objects(mp4 files, jpgs, mp3s, ...) Amazon S3
5. Autoscale servers
6. Create k8 clusters
   ...

# EC2 Servers (Elastic compute version 2)

VMs on AWS are called EC2 Servers

1. Elastic - Can increase/decrease the size of the machine
2. Compute - It is a machine

### Create new Key Pair (ssh (secure shell))

- So you login from anywhere(certificate has access to connect from anywhere)

```sh
chmod 700 <pem file>
```

- change file or directory permissions. It modifies the read (r), write (w), and execute (x) permissions for the file owner, group, and others.

```sh
ssh -i <pem file> ubuntu@<respected ip>
```

### Network Settings

- Allow SSH traffic from Anywhere
- Allow HTTPS traffic from the internet -> port 443
- Allow HTTP traffic from the internet -> port 80

http://1.2.34 same as -> 1.2.34:80
https://1.2.34 same as -> 1.2.34:443

- Good practice to only allow port 443, https

### Change Inbound rules

- Open more ports to get request on that port (eg- 8080)
- It act as virtual firewall

# AWS S3 (Simple Storage Service)

- Objects(video, audio, jpg, png) are store in a cloud storage.

# CDNs

- A Content Delivery Networks (CDN) is a distributed network of servers strategically located around the globe that work together to deliver digital content (like web pages, images, videos, and scripts) to users more efficiently. CDNs reduce the distance between the server and the user, improving website loading times, reliability, and performance.

- Storage - Object Stores
- Distribution - CDNs
- When I ask certain video all the time, it cached in my nearest server(pos - point of presence) and then come from there. When not wanted the caches got cleared.
- This is manage by cloudfront.
- I don't req to S3 link directly, first I request cloudfront url, that is point to that S3 storage.

> Storage -> 2Gb -> 0.01$
> Distribution -> 20gb -> 0.01$ , Distribution is always higher

- For Frontend, mp4 files, images, ** Object Stores + CDNs** are better approach
