# Containerlab Hello World
This is the proverbial hello-world for [Containerlab](https://containerlab.dev/). A simple topology that deploys two Linux containers connected to each other and validate that connectivity exist.
The minimal topology is:
```
   ┌─────────┐                 ┌─────────┐       
   │         │ 10.0.0.1        │         │       
   │ client1 │─────────────────│ client2 │       
   │         │        10.0.0.2 │         │       
   └─────────┘                 └─────────┘       
```

## How to?
Deploy directly without downloading from Containerlab
```
containerlab deploy -t https://github.com/nardusleroux/clab-helloworld
```

or, download first and then deploy from local directory

```
git clone https://github.com/nardusleroux/clab-helloworld
cd clab-helloworld
containerlab deploy
```

Validate your Containerlab installation by executing a connectivity check from client1 to client2
```
docker exec clab-clab-helloworld-client1 ping 10.0.0.2
```

Once done, destroy the lab by performing:
```
containerlab destroy -t https://github.com/nardusleroux/clab-helloworld
```
