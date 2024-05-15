
# Documentación Mejorada por Z0SO

## Instalación

Para empezar, instala el paquete utilizando el gestor de paquetes correspondiente a tu distribución. Si estás utilizando Arch Linux, puedes instalarlo con el siguiente comando:

```bash 
sudo pacman -S fastfetch 
```

Una vez instalado, simplemente ejecuta el siguiente comando en tu terminal:

```bash
fastfetch
```

Aquí está el apartado de "Uso" mejorado para tu documentación README:

# Como usar Fastfetch

- Ejecute Fastfetch con la configuración predeterminada:
```bash
fastfetch
```

- Ejecute Fastfetch con todos los módulos compatibles y encuentre lo que le interesa:
```bash
fastfetch -c all.jsonc
```

- Encuentre todos los datos que detecta Fastfetch y muestrelos en formato JSON:
```bash
fastfetch -s <modulo> --format json
```

- Muestre mensajes de ayuda:
```bash
fastfetch --help
```

- Genere el archivo de configuración basado en los argumentos de línea de comandos:
```bash
fastfetch --arg1 --arg2 --gen-config
```



# Personalización

*Fastfetch* permite una personalización completa a través de JSONC (JSON con comentarios) para su configuración. 

*Para obtener más detalles sobre la configuración, consulta su [Wiki](https://github.com/fastfetch-cli/fastfetch/wiki/Configuration).* 

## Parte de la Estructura del Texto
También proporcionamos algunos archivos de configuración predefinidos en la carpeta [`presets`](https://github.com/fastfetch-cli/fastfetch/blob/dev/presets), que incluyen los utilizados para las capturas de pantalla anteriores. Puedes cargarlos usando la opción `-c <nombre_archivo>`. 

Tambien puedes explorar en la carpeta presets de aqui, es una copia de la original para tenerla mas a mano. Pero recomiendo que visites el link oficial que esta deje arriba ya que esto no es mio. :3

Estos archivos pueden servir como ejemplos útiles para entender los argumentos de formato.
#### Para configurar la Estructura
Ejecuta este comando:

```bash
fastfetch --gen-config  

The generated config file has been written in `/home/<user>/.config/fastfetch/config.jsonc`
```

Luego iras a la carpeta de [`presets`](https://github.com/fastfetch-cli/fastfetch/blob/dev/presets), este es el archivo de configuracion en el cual cargara los estilos.

Puedes elegir cualquier `jsonc` que este ahi o crear uno y personalizarlo a tu manera.

- Te recomiendo que copies el codigo de uno de esos que te guste y lo pegues en el archivo ***config.jsonc***  que probablemente se encuentre en `/home/<user>/.config/fastfetch/config.jsonc` reemplazando `<user>` por tu nombre de usuario. Si no lo encuentras es probable que tengas que ejecutar  `fastfetch --gen-config` que esta arriba.

# Personalizacion del Logotipo

Además, los logotipos son altamente personalizables. 

Consulta la [documentación del logotipo](https://github.com/fastfetch-cli/fastfetch/wiki/Logo-options) para obtener más información sobre cómo personalizarlos.


#### Ejemplo de Como Hacerlo

Aqui voy a explicar el ejemplo de como agregar un logotipo para *Arch Linux*, si estas usando otras distribuciones no deben cambiar mucho, porque simplemente es editar el mismo archivo `jsonc` que utilizamos anteriormente para configurar la estructura de nuestro **fastfetch**


Voy a dejarte el codigo `jsonc` de como lo tengo configurado para que simplemente lo reemplaces en tu propio archivo de configuracion, solo asegurate de cambiarle el nombre "home/zoso/.." por tu nombre de usuario.

Aqui te proporciono el fragmento mas importante de este codigo `conf.jsonc`

```json
    "$schema": "https://github.com/fastfetch-cli/fastfetch/raw/dev/doc/json_schema.json",
    "logo": {

	"source": "$(ls ~/.config/fastfetch/img/Arch-linux-logo.png | shuf -n 1)",
	"width": 32,
	"height":16,
        "padding": {
            "top": 4,
	    "left":2,
        }
    },
```

Nota que lo que tu debes hacer es adentro de logo pegar el path que haga referencia a la imagen .png que quieres que se muestre cuando ejecutes fastfetch.
En mi caso en la misma carpeta `~/.config/fastfetch/`cree una carpeta `/img` donde puse la imagen png, por lo tanto la linea de codigo te queda asi:

```json
"source": "$(ls ~/.config/fastfetch/img/<nombre-de-tu-imagen>.png | shuf -n 1)"
```

Luego solo te queda jugar con width, height, el padiding y las posiciones a tu gusto.
Si quieres hilar muy fino puedes leer la documentacion que te proporcione arriba para que puedas leerlo.

---
