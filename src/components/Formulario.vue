<template>
    <div class="container">
        <h1>Formulario Desafio</h1>
        <div class="row">
            <div class="col-6 mt-2 bg-color-vueDark text-white">
                <form class="p-3">
                    <!-- Color de Fondo -->
                    <div class="row mb-3">
                        <label class="col-sm-12 col-form-label">Color de Fondo</label>
                        <div class="col-sm-12">
                            <input v-model="backgroundColor" class="form-control" type="text"
                                placeholder="Escribe el nombre del color" />
                        </div>
                    </div>

                    <!-- Color del Texto -->
                    <div class="row mb-3">
                        <label class="col-sm-12 col-form-label">Color del Texto</label>
                        <div class="col-sm-12">
                            <input v-model="textColor" class="form-control" type="text"
                                placeholder="Escribe el nombre del color" />
                        </div>
                    </div>

                    <!-- Mostrar Texto -->
                    <div class="row mb-3">
                        <label>
                            Mostrar texto <br>
                            <input type="checkbox" v-model="showText" />
                        </label>
                    </div>

                    <!-- Border Redondeado -->
                    <div class="row mb-3">
                        <label>
                            Ajustar borde redondeado:
                            <input type="range" v-model="borderRadius" min="0" max="100" />
                        </label>
                    </div>

                    <!-- Textarea para ingresar contenido textual -->
                    <div class="row mb-3">
                        <label class="col-sm-12 col-form-label">
                            Contenido Textual:
                            <textarea class="form-control" v-model="contentText" rows="2"
                                placeholder="Escribe el contenido para mostrar en el contenedor"></textarea>
                        </label>
                    </div>


                    <!-- Select para elegir el tipo de tipografía -->
                    <div class="row mb-3">
                        <label for="fontType">
                            Selecciona la tipografía:
                            <select v-model="fontFamily" id="fontType">
                                <option value="cursive">Cursive</option>
                                <option value="serif">Serif</option>
                                <option value="sans-serif">Sans-serif</option>
                                <option value="monospace">Monospace</option>
                                <option value="fantasy">Fantasy</option>
                            </select>
                        </label>
                    </div>

                    <!-- Checkbox para aplicar opacidad -->
                    <div class="row mb-3">
                        <label>
                            Aplicar opacidad <br />
                            <input type="checkbox" v-model="isOpaque" />
                        </label>
                    </div>


                    <!-- Radio buttons para elegir el tamaño del texto -->
                    <label>
                        Tamaño de la letra: <br />
                        <input type="radio" v-model="fontSize" value="12px" /> Pequeño
                        <input type="radio" v-model="fontSize" value="16px" /> Mediano
                        <input type="radio" v-model="fontSize" value="20px" /> Grande
                    </label>

                </form>
            </div>
            <div class="col-6 mt-2 bg-color-vueLight text-warning text-center d-flex justify-content-center align-items-center">
                <!-- Contenedor div que cambia de color, texto, borde redondeado y tipografía según los inputs -->
                <div :style="{
                    backgroundColor: backgroundColor,
                    color: textColor,
                    borderRadius: borderRadius + 'px',
                    fontFamily: fontFamily,
                    opacity: isOpaque ? 0.5 : 1,
                    fontSize: fontSize
                }" class="color-container p-3">
                    <!-- Muestra el texto solo si el checkbox está seleccionado -->
                    <div v-if="showText">
                        {{ contentText }}
                    </div>
                </div>
            </div>

        </div>
    </div><br>
    <footer>Desarrollado por Boris Guiñez 2024</footer>
</template>

<script>

export default {
    name: "Formulario",

    data() {
        return {
            backgroundColor: "", // Almacena el valor del color ingresado,
            textColor: "", // Almacena el valor del color del texto,
            showText: false, // Controla si se muestra o no el texto
            borderRadius: 0, // Almacena el valor del border-radius en píxeles
            contentText: "", // Almacena el contenido del textarea
            fontFamily: "cursive", // Almacena el tipo de tipografía seleccionada
            isOpaque: false, // Controla si el contenedor tiene opacidad
            fontSize: "16px", // Almacena el tamaño de la fuente seleccionada
        }

    },

}

</script>


<style>
/* Estilos para el contenedor */
.color-container {
    width: 200px;
    height: 200px;
    margin-top: 20px;
    border: 1px solid #ccc;
    display: flex;
    justify-content: center;
    align-items: center;
}

.bg-color-vueDark {
    background-color: rgb(13, 66, 66);
}
.bg-color-vueLight {
    background-color: rgb(29, 155, 155);
}
</style>