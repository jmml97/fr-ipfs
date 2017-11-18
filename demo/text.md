Asumimos que tenemos IPFS instalado.

Inicializamos el nodo IPFS `ipfs init`. Generará el *keypair* y creará un repositorio.

`peer identity` es el *hash* de la clave pública.

Directorio demo con algunos archivos.

`ipfs add -r .` añade todo el directorio a IPFS. Nos muestra los *hashes* de los archivos.

Si dos archivos tienen el mismo *hash* es porque son iguales.

`ipfs ls <hash del directorio>` nos muestra los archivos del directorio que acabamos de añadir.

`ipfs cat <hash de un archivo>` nos muestra el contenido del archivo.
Podemos hacer `ipfs cat <hash de un archivo> > <nombre archivo local>` para guardar los contenidos en un archivo que podemos abrir.

Podemos iniciar el *daemon* IPFS con `ipfs daemon`, que iniciará el servidor IPFS.

Si hacemos `ipfs id` nos mostrará información sobre nuestro nodo IPFS, incluyendo la clave pública.

`ipfs swarm peers` nos muestra a qué otros nodos estamos conectados. Podemos obtener  información de estos nodos con `ipfs id <hash>`.

Podemos acceder al servidor desde `localhost:8080/ipfs/<hash>`, siendo `<hash>` el hash del archivo al que queremos acceder.

Podemos acceder igualmente al contenido de nuestro ordenador desde otro *gateway* de IPFS.

Por ejemplo, al mismo archivo de antes podemos acceder con su *hash*. Un *gateway* es `gateway.ipfs.io/ipfs/<hash>`. Lo que esto hace es hará una petición, buscando en la DHT el archivo, contactará con mi ordenador y bajará el archivo.

De igual forma, utilizando nuestro servidor local podemos acceder a archivos que se encuentran en otros nodos. Por ejemplo, si queremos acceder a una copia de la Wikipedia en IPFS simplemente hacemos `localhost:8080/ipfs/<hash de la wikipedia>`.

Podemos acceder a la interfaz web con `127.0.0.1:5000/webui`.