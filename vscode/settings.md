# Configuración de Visual Studio Code

Este documento contiene recomendaciones y ejemplos de configuración detallados para optimizar el uso de Visual Studio Code. Se incluyen ajustes generales, atajos de teclado y configuraciones específicas de extensiones para mejorar la productividad y personalización del entorno de desarrollo.

## Configuración global

Este apartado define la configuración general del editor, incluyendo opciones del editor de texto, atajos de teclado, interfaz de la ventana y ajustes de espacio de trabajo.

### Editor

Opciones relacionadas con la apariencia y comportamiento del editor de texto, incluyendo el tamaño de fuente, la detección de sangría y la disposición del minimapa.

```jsonc
"editor.colorDecorators": false,                             // Deshabilitar selectores de color.
"editor.detectIndentation": false,                           // Deshabilitar detección de sangría.
"editor.fontSize": 13,                                       // Tamaño de la fuente.
"editor.minimap.side": "left",                               // Colocar el minimapa a la izquierda.
"editor.multiCursorModifier": "ctrlCmd",                     // Usar Ctrl/Cmd para crear múltiples cursores.
"editor.stickyScroll.defaultModel": "indentationModel",      // Usar modelo de desplazamiento adhesivo por sangría.
"editor.tabSize": 2,                                         // Tamaño de la tabulación.
```

### Teclado

Configuración del comportamiento del teclado y la forma en que se procesan los eventos de entrada.

```jsonc
"keyboard.dispatch": "keyCode",                              // Modo de procesamiento de eventos de teclado.
```

### Ventana

Ajustes de la interfaz de la ventana de Visual Studio Code, como el estilo de la barra de título.

```jsonc
"window.titleBarStyle": "custom",                            // Estilo de la barra de título.
```

### Espacio de trabajo

Configuraciones relacionadas con la distribución y disposición de las barras y paneles dentro del entorno de trabajo.

```jsonc
"workbench.activityBar.location": "top",                     // Posición de la barra de actividades.
"workbench.sideBar.location": "right",                       // Posición de la barra lateral.
```

### Git

Configuración relacionada con Git y repositorios de código.

```jsonc
"git.defaultBranchName": "main",                             // Nombre predeterminado para nuevas ramas.
```

## Ajatos de teclado

Configuración de combinaciones de teclas personalizadas para mejorar la eficiencia en el uso del editor.

```jsonc
{
  "key": "shift+alt+f",                                      // Shift + Alt + F
  "command": "editor.action.formatDocument",                 // Formatea el documento.
  "when": "editorTextFocus && !editorReadonly",              // Cuando el editor está enfocado y no es de solo lectura.
},              
{              
  "key": "*",                                                // Cualquier tecla
  "command": "-editor.action.formatDocument",                // Deshabilita el comando predeterminado.
},              
{              
  "key": "ctrl+shift+c",                                     // Ctrl + Shift + C
  "command": "editor.action.commentLine",                    // Comenta la línea.
  "when": "editorTextFocus && !editorReadonly",              // Cuando el editor está enfocado y no es de solo lectura.
},              
{              
  "key": "*",                                                // Cualquier tecla
  "command": "-editor.action.commentLine",                   // Deshabilita el comando predeterminado.
},              
{              
  "key": "alt+s",                                            // Alt + S
  "command": "codesnap.start",                               // Inicia la captura de pantalla.
  "when": "editorTextFocus && !editorReadonly",              // Cuando el editor está enfocado y no es de solo lectura.
},
```

## Extensiones y configuración específica

Esta sección abarca la configuración de extensiones específicas instaladas en Visual Studio Code, detallando su propósito y los parámetros clave que afectan su comportamiento.

### CodeSnap

Extensión que permite capturar capturas de pantalla de fragmentos de código con un diseño atractivo y personalizable.

> **Name**: CodeSnap\
> **Id**: adpyke.codesnap\
> **Description**: 📷 Take beautiful screenshots of your code\
> **Version**: 1.3.4\
> **Publisher**: adpyke\
> **VS Marketplace Link**: https://marketplace.visualstudio.com/items?itemName=adpyke.codesnap

```jsonc
"codesnap.backgroundColor": "transparent",                   // Usar fondo transparente.
"codesnap.boxShadow": "#0009 0 .25em .75em",                 // Sombra del recuadro.
"codesnap.containerPadding": "1em",                          // Espaciado del contenedor.
"codesnap.realLineNumbers": true,                            // Usar números de línea reales.
"codesnap.roundedCorners": true,                             // Usar bordes redondeados.
"codesnap.showWindowControls": false,                        // Ocultar controles de ventana.
"codesnap.showWindowTitle": true,                            // Mostrar título de ventana.
```

### Cyber Dev Colors

Extensión que permite establecer un tema personalizado para el editor.

> **Name**: Cyber Dev Colors  
> **Id**: adetena.cyber-dev-colors  
> **Description**: Cyber developer color theme.  
> **Version**: 1.0.4  
> **Publisher**: adetena  
> **VS Marketplace Link**: https://marketplace.visualstudio.com/items?itemName=adetena.cyber-dev-colors

```jsonc
"workbench.colorTheme": "Cyber Dev",                         // Tema de color del área de trabajo.
```

### GitHub Copilot + GitHub Copilot Chat

Extensiones de inteligencia artificial para asistencia en la programación mediante sugerencias de código y chat interactivo.

> **Name**: GitHub Copilot\
> **Id**: GitHub.copilot\
> **Description**: Your AI pair programmer\
> **Version**: 1.266.0\
> **Publisher**: GitHub\
> **VS Marketplace Link**: https://marketplace.visualstudio.com/items?itemName=GitHub.copilot

```jsonc
"github.copilot.enable": {                                   // Configuración de GitHub Copilot para lenguajes específicos.
  "markdown": true,                                          // Habilitar GitHub Copilot para Markdown.
},
```

> **Name**: GitHub Copilot Chat\
> **Id**: GitHub.copilot-chat\
> **Description**: AI chat features powered by Copilot\
> **Version**: 0.24.0\
> **Publisher**: GitHub\
> **VS Marketplace Link**: https://marketplace.visualstudio.com/items?itemName=GitHub.copilot-chat

```jsonc
"github.copilot.chat.localeOverride": "es",                  // Anula la configuración de la región del sistema.
```

### Todo Tree

Extensión que permite resaltar y organizar comentarios con etiquetas como TODO, FIXME, WARN, facilitando la gestión de tareas dentro del código.

> **Name**: Todo Tree\
> **Id**: Gruntfuggly.todo-tree\
> **Description**: Show TODO, FIXME, etc. comment tags in a tree view\
> **Version**: 0.0.226\
> **Publisher**: Gruntfuggly\
> **VS Marketplace Link**: https://marketplace.visualstudio.com/items?itemName=Gruntfuggly.todo-tree

```jsonc
"todo-tree.general.tags": [                                  // Etiquetas utilizadas en los comentarios.
  " edit ",                                                  // Etiqueta para anotaciones de edición.
  " info ",                                                  // Etiqueta para notas informativas.
  " todo ",                                                  // Etiqueta para tareas pendientes.
  " warn ",                                                  // Etiqueta para resaltar puntos críticos.
],
"todo-tree.highlights.defaultHighlight": {                   // Resaltado predeterminado de etiquetas.
  "borderRadius": "1em",                                     // Usar bordes redondeados.
  "gutterIcon": true,                                        // Mostrar icono en el margen.
  "type": "tag",                                             // Resaltar etiqueta.
},
"todo-tree.highlights.customHighlight": {                    // Estilos de resaltado personalizados para cada etiqueta.
  " edit ":{                                                 // Estilo de la etiqueta " edit ".
    "background": "#0f9",                                    // Fondo turquesa.
    "foreground": "#000",                                    // Texto negro.
    "icon": "pencil",                                        // Icono de lápiz.
    "iconColour": "#0f9",                                    // Icono turquesa.
  },
  " info ": {                                                // Estilo de la etiqueta " info ".
    "background": "#09f",                                    // Fondo azul.
    "foreground": "#000",                                    // Texto negro.
    "icon": "info",                                          // Icono de información.
    "iconColour": "#09f",                                    // Icono azul.
  },
  " todo ": {                                                // Estilo de la etiqueta " todo ".
    "background": "#fff",                                    // Fondo blanco.
    "foreground": "#000",                                    // Texto negro.
    "icon": "checklist",                                     // Icono de lista de tareas.
    "iconColour": "#fff",                                    // Icono blanco.
  },
  " warn ": {                                                // Estilo de la etiqueta " warn ".
    "background": "#fd0",                                    // Fondo amarillo.
    "foreground": "#000",                                    // Texto negro.
    "icon": "alert",                                         // Icono de alerta.
    "iconColour": "#fd0",                                    // Icono amarillo.
  },
},
```

## Ejemplo

El repositorio contiene un archivo [settings.jsonc](./settings.jsonc) completo y comentado a modo de demostración, así como un archivo [settings.json](./settings.json), que reúne todas estas configuraciones en un solo lugar para su fácil implementación en Visual Studio Code. Además se incluyen archivos similares para los atajos de teclado en [keybindings.jsonc](./keybindings.jsonc) y [keybinginds.json](./keybindings.json).

