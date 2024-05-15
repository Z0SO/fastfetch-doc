¡Claro! Aquí tienes una versión mejorada de tu documentación README:

---

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



## Personalización

*Fastfetch* permite una personalización completa a través de JSONC (JSON con comentarios) para su configuración. 

*Para obtener más detalles sobre la configuración, consulta su [Wiki](https://github.com/fastfetch-cli/fastfetch/wiki/Configuration).* 

## Parte de la Estructura del Texto
También proporcionamos algunos archivos de configuración predefinidos en la carpeta [`presets`](https://github.com/fastfetch-cli/fastfetch/blob/dev/presets), que incluyen los utilizados para las capturas de pantalla anteriores. Puedes cargarlos usando la opción `-c <nombre_archivo>`. 

Tambien puedes explorar en la carpeta presets de aqui, es una copia de la original para tenerla mas a mano. Pero recomiendo que visites el link oficial que esta deje arriba ya que esto no es mio. :3



Estos archivos pueden servir como ejemplos útiles para entender los argumentos de formato.

Debes darle al siguiente comando
```bash
fastfetch --gen-config  

The generated config file has been written in `/home/<user>/.config/fastfetch/config.jsonc`
```

- Luego iras a la carpeta de [`presets`](https://github.com/fastfetch-cli/fastfetch/blob/dev/presets), este es el archivo de configuracion en el cual cargara los estilos.
- puedes elegir cualquier jsonc que este ahi o crear uno y personalizarlo a tu manera.
- Te recomiendo que copies el codigo de uno de esos que te guste y lo pegues en `/home/<user>/.config/fastfetch/config.jsonc` reemplazando `<user>` por tu nombre de usuario.


## Personalizacion del Logotipo

Además, los logotipos son altamente personalizables. 

Consulta la [documentación del logotipo](https://github.com/fastfetch-cli/fastfetch/wiki/Logo-options) para obtener más información sobre cómo personalizarlos.


---
