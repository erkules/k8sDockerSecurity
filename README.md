# Kubernetes und Docker Security

Von und zu Runtimegeschichten

Agenda:

* Was kritisch bei Docker ist
* Desgleichen in K8s/OCP und etwas mehr
* PSP/SCC to the rescue
* Abgesang auf PSP

# Was kritisch bei Docker ist

Mounts/Privilegiert/(Linux)Namespaces/USER

~~~
docker container run --rm -v /etc/:/srv/ alpine cat /srv/passwd
docker container run --rm -v /proc:/host/proc --privileged -ti alpine
docker container run --rm -ti --pid host alpine
docker container run --rm -ti --net host alpine
docker container run --rm -ti --user 1000 alpine
docker container run --rm -ti --user 1235  erkules/ping
~~~

# Desgleichen in K8s/OCP und etwas mehr

Eigentlich nur pod-max-privileged.yaml anschauen :)


# PSP/SCC to the rescue

Beispiele mit PSP (ohne Rolebinding)

SCC zeigen

# Abgesang auf PSP

Fahrplan laut Formalie 


Deprecated ab K8s 1.21 (Sommer)

Weg        ab K8s 1.25 (Sommer +2 Jahre)

SCC bleibt

# OPA/kyverno to the rescue

Nächster Talk

