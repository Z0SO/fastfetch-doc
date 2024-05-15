¡Claro! Aquí tienes una versión mejorada de tu documentación README:

---

# Documentación

## Instalación

Para empezar, instala el paquete utilizando el gestor de paquetes correspondiente a tu distribución. Si estás utilizando Arch Linux, puedes instalarlo con el siguiente comando:

```bash 
sudo pacman -S fastfetch 
```

Una vez instalado, simplemente ejecuta el siguiente comando en tu terminal:

```bash
fastfetch
```

## Personalización

*Fastfetch* permite una personalización completa a través de JSONC (JSON con comentarios) para su configuración. 

Para obtener más detalles sobre la configuración, consulta nuestra [Wiki](https://github.com/fastfetch-cli/fastfetch/wiki/Configuration). 

## Parte de la Estructura del Texto
También proporcionamos algunos archivos de configuración predefinidos en la carpeta [`presets`](https://github.com/fastfetch-cli/fastfetch/blob/dev/presets), que incluyen los utilizados para las capturas de pantalla anteriores. Puedes cargarlos usando la opción `-c <nombre_archivo>`. 

Estos archivos pueden servir como ejemplos útiles para entender los argumentos de formato.

Debes darle al siguiente comando
```bash
fastfetch --gen-config  

The generated config file has been written in `/home/<user>/.config/fastfetch/config.jsonc`
```

Luego iras a la carpeta de [`presets`](https://github.com/fastfetch-cli/fastfetch/blob/dev/presets), este es el archivo de configuracion en el cual cargara los estilos.




## Personalizacion del Logotipo

Además, los logotipos son altamente personalizables. Consulta la [documentación del logotipo](https://github.com/fastfetch-cli/fastfetch/wiki/Logo-options) para obtener más información sobre cómo personalizarlos.


---

# Wiki de Fastfetch
# Configuración basada en JSON

Fastfetch utiliza JSONC (JSON con comentarios) para la configuración, la cual debe estar ubicada en `~/.config/fastfetch` y nombrada `config.jsonc` (NO `config.json`). Puedes generar este archivo de configuración usando el comando `fastfetch --gen-config`. Un ejemplo básico de archivo JSONC se muestra a continuación:

```jsonc
// ~/.config/fastfetch/config.jsonc
{
    "$schema": "https://github.com/fastfetch-cli/fastfetch/raw/dev/doc/json_schema.json",
    "modules": [
        "title",
        "separator",
        "module1",
        {
            "type": "module2",
            "module2-option": "value"
        }
    ]
}
```

Se recomienda utilizar un editor con soporte de esquema JSON. Si no estás seguro, se sugiere usar Visual Studio Code.

## Migración desde configuraciones basadas en banderas

Asegúrate de que `~/.config/fastfetch/config.jsonc` no exista antes de generar un nuevo archivo de configuración:

```bash
fastfetch --whatever-flags --gen-config
```

## ¿Por qué usar JSON?

Aunque teníamos una configuración basada en líneas de comandos durante mucho tiempo, ¿por qué molestarse en introducir un nuevo formato de configuración?

- JSON es un estándar con soporte en la mayoría de los IDEs.
- La estructura de JSON es más legible con la sangría adecuada.
- Con el esquema JSON, se obtiene la inteligencia de IDE mientras escribes.
- JSON admite arrays, permitiendo imprimir un módulo múltiples veces sin complicaciones.

Para más información sobre el esquema JSON, consulta: [Json-Schema](https://github.com/fastfetch-cli/fastfetch/wiki/Json-Schema).

## Documentación adicional

- Puedes encontrar ejemplos de configuraciones en: [examples](https://github.com/fastfetch-cli/fastfetch/tree/dev/presets/examples). Prueba uno con `fastfetch --config examples/x.jsonc`.
- Para una explicación más detallada, consulta `fastfetch --help`.

## Notas

- Cuando `config.jsonc` está presente, `config.conf` será ignorado.
- Mezclar banderas de línea de comandos con `config.jsonc` puede o no puede funcionar. Generalmente, las banderas de opción de la línea de comandos del módulo no funcionarán cuando se usa `config.jsonc`. Otras banderas deberían funcionar.
- Los caracteres especiales deben ser codificados como `\uXXXX` en JSON. En particular, `\e` o `\033` debería ser `\u001b`.

---

Esta versión ofrece una estructura más organizada y claridad en los puntos clave. ¿Qué piensas?