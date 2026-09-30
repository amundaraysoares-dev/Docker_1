# 📝 Informe de Práctica: Gestión de Contenedores Docker

---
(improtante solo hay uso de ia para la decoracion del marckdown, prompt: "Pon el marckdown bonito")
### **1. Descarga la imagen de Alpine sin arrancarla y comprueba que la tienes. Fija la versión: no uses `latest`. Escoge una versión de las disponibles en Docker Hub.**

Para la descarga de Alpine hay que usar el siguiente comando. La versión que elegí es: **`3.22`**

![foto](docker_1/Captura%20desde%202026-09-30%2009-46-45.png)

Aquí la comprobación de que sí está instalada, y el comando para poder verlo es `docker images`.

![foto](docker_1/Captura%20desde%202026-09-30%2009-47-36.png)

---

### **2. Crea un contenedor sin nombre y sin arrancarlo. ¿En qué estado queda? ¿Qué nombre le ha puesto Docker?**

Para la creación del contenedor solo tendremos que hacer lo siguiente:

![foto](docker_1/Captura%20desde%202026-09-30%2009-56-12.png)

Ahora, con el comando `docker ps -a`, vamos a revisar cómo quedó el contenedor. En este caso, podemos ver que está en estado **`creado`** y el nombre que le asignó automáticamente Docker fue **`quizzical_mendel`**.

![foto](docker_1/Captura%20desde%202026-09-30%2009-57-48.png)

---

### **3. Crea y arranca `dam_alp1` con una shell. ¿Qué opciones necesitas para poder escribir dentro?**

Se necesita el **`-i`**, ya que le permite al contenedor recibir lo que escribes por teclado, y el **`-t`**, que hace que se cree una pseudo-terminal simulada del contenedor.

![foto](docker_1/Captura%20desde%202026-09-30%2010-01-33.png)

---

### **4. Desde dentro, mira qué IP tiene y si puede hacer ping a `google.com`.**

Aquí podemos ver que tiene de IP **`172.17.0.2`** y que efectivamente sí que puede hacer ping a Google.

![foto](docker_1/Captura%20desde%202026-09-30%2010-02-30.png)

---

### **5. Deja `dam_alp1` funcionando sin pararlo y crea `dam_alp2` igual. Con los dos en marcha, haz ping de uno a otro: por IP y por nombre. Explica cada resultado.**

Abro una segunda terminal y creo otro contenedor. Ahora pruebo a hacer los pings:

* **Con IP:** Da el resultado esperado: un ping normal sin pérdida de paquetes.
* **Con el nombre:** Da error, ya que en el funcionamiento del servidor de Docker no tiene resolución de nombres DNS. Eso hace que no se pueda entender el nombre de mi otro contenedor.

![Captura desde 2026-09-30 10-51-12.png](docker_1/Captura%20desde%202026-09-30%2010-51-12.png)
![foto](docker_1/Captura%20desde%202026-09-30%2010-07-12.png)

---

### **6. Con los dos en marcha, averigua cuánta memoria consumen. ¿Hay un comando de Docker para eso?**

Sí, tenemos el `docker stats`, el cual nos permite ver la información de los contenedores y, entre ellos, se encuentra la memoria que usan.

![foto](docker_1/Captura%20desde%202026-09-30%2010-08-36.png)

---

### **7. Sal con `exit`. ¿Qué les ha pasado? Repite el comando anterior: ¿qué ves ahora y por qué?**

Al salir de los contenedores se cierran automáticamente, lo que causa que al revisar el status no nos dé ninguna información, ya que no se encuentran activos.

![foto](docker_1/Captura%20desde%202026-09-30%2010-09-10.png)

---

### **8. ¿Cuánto disco has ocupado? Distingue imágenes de contenedores.**

Las imágenes han ocupado **8.29 MB** de memoria, pero los contenedores no ocupan nada.

![foto](docker_1/Captura%20desde%202026-09-30%2010-12-51.png)

# Docker_1
