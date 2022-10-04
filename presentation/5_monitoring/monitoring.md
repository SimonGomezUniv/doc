---
theme : "night"
transition: "slide"
highlightTheme: "monokai"
#logoImg: "logo.png"
slideNumber: false
title: "Micoservice & Monitoring"


---
<style>
img {
    width:80%;
}
</style>

# I ❤ Logs

---

![history](./history.gif)

---

![logs](log_web.png)

---

<style>
img[alt=gandalf] {
    width:30%;
}
img[alt=server] {
    width:60%;
}
</style>

![server](servers.jpeg)
![gandalf](gandalf.jpeg){.fragment .fade-down}

---

<!-- .slide: data-background="#dddddd" -->

More than 60 applications 

```mermaid
%%{init: {'theme': 'base', "flowchart" : { "curve" : "basis" } } }%%
flowchart LR
    outil(Web Consultation Tool)
    outil-->app1
    outil-->app2
    outil-->app3
    subgraph Servers
    app1(fa:fa-file Application 1)
    app2(Application 2)
    app3(Application 3)
    end

```

---

![sma](sma.png)

---

![sma](sma_search.png)

---

![ift](ift2.jpg)

---

![soca](soca.jpg)

---

![soca 2](soca2.jpg)

---

![big data](bigdata.jpg)

---

<!-- .slide: data-background="#dddddd" -->

```mermaid
%%{init: {'theme': 'base', "flowchart" : { "curve" : "basis" } } }%%
flowchart LR

    subgraph Servers
    app1(Application 1 fa:fa-file )
    app2(Application 2 fa:fa-file )
    app3(Application 3 fa:fa-file )
    end
    outil(Web Consultation Tool)
    outil-->app1
    outil-->app2
    outil-->app3

    subgraph Datalake
    hdfs[(HDFS)]
    el[(Elastic Search)]
    end

    kafka{kafka}

    app1-->kafka
    app2-->kafka
    app3-->kafka

    kafka-->hdfs
    kafka-->el
```

---

![kibana](kibana.jpg)

---

![machine learning](ml.jpg)

---

## Opentelemetry

https://opentelemetry.io/docs/
![opentelemetry](opentelemetry.png)

---

## Logs


<span style="font-size: .9rem">
I, [2021-02-23T13:26:23.505892 #22473]  INFO -- : [6459ffe1-ea53-4044-aaa3-bf902868f730] Started GET "/" 
</span>

---

## Span

![flame](flamegraph.png)

---

## Metrics

![metrics](metrics.jpg)

---

![scyfy](scify.gif)

---

# TD

---

## TD 
![td_loki](td_loki.jpg)

---

## TD 
![td_grafana](td_grafana.jpg)

---

## TD 
![td_prom](td_prom.jpg)

---

# TD
https://simongomezuniv.github.io/td_monitoring