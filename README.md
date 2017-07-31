# Time2Code
A portable, scaleable web based code editor to integrate into your code learning experiences.

The goal is to make deploying your own web based code editor easier and more fun.

## Tech Overview
* The Code execution backend is built off of the serverless [FaaS](http://docs.get-faas.com/) Framework for scalability and ability to support many languages.  Although support for [k8s](https://kubernetes.io/) is currently being tested on [faas-netes](https://github.com/alexellis/faas-netes) and this project and appears to be fairly successful, currently primary support is on Docker Swarm.

* Function handling and code excution are being handled by Python processes.  Python handles the STDIN of all of the function requests and then passes it to the desired language for interpretation and execution or compilation and execution.

* Web site is being driven by the [Flask](http://flask.pocoo.org/) Framework as a Swarm service.

* Code editor is built from [Ace Editor](https://ace.c9.io/) project.

* Terminal is built from [XTermJS](https://xtermjs.org/).

## Up and Running

The following snippet will initialize your swarm, Time2Code, FaaS and Time2code functions.

```sh
docker swarm init --advertise-addr eth0 && \
  git clone https://github.com/JockDaRock/Time2Code && \
  cd Time2Code && \
  bash time2deploy.sh && \
  docker service ls
```

If you are on your laptop navigate to http://127.0.0.1:5555 and start coding.

![](images/python_sample0.png)

### Coding Languages Currently Supported

* Python, Golang, Powershell, NodeJS, ... more coming very soon.

* Currently working on... I am currently working C# code excution. Most of my tests are running well, but need to iron out some necessary dependancies and other issues.


## Roadmap and Contributing

Time2Code is written mostly in Python and is MIT licensed - contributions are welcomed whether that means providing feedback, testing existing and new feature or hacking on the source. To get started you can checkout the roadmap and contribution guide or browse the open issues on Github.

