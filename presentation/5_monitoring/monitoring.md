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
