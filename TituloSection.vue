<script lang="ts">
import { defineComponent, ref } from "vue";
defineComponent({
    props: {
        sectionTitle: {
            type: String,
            required: true,
        },

        sectionTitleLargo: {
            type: String,
            required: false,
        },
        extra: {
            type: String,
            required: false,
        },
        section: {
            type: String,
            required: true,
        },
        favoritos: {
            type: String,
            required: false,
        },
        guardados: {
            type: String,
            required: false,
        },
        cambiar_clave: {
            type: String,
            required: false,
        },
    },
    setup() {
        const cardsFavoritos = ref(null);
        return {
            cardsFavoritos,
            scrollToCards() {
                alert("scrollToCards");
                // Obtener el elemento referenciado
                const el = this.cardsFavoritos.value;
                // Verificar que el elemento existe
                if (el) {
                    // Desplazar el elemento a la vista
                    el.scrollIntoView({ behavior: "smooth" });
                }
            },
        };
    },
});
</script>

<template>
    <template v-if="section === 'MI-CUENTA_PRINCIPAL'">
        <h1 class="section-title">{{ sectionTitle }}</h1>
        <div class="d-flex align-items-center justify-content-center">
            <a href="" class="botones_cuenta">{{ favoritos }}</a>
            <a href="" class="botones_cuenta">{{ guardados }}</a>
            <a href="" class="botones_cuenta">{{ cambiar_clave }}</a>
        </div>
    </template>
    <template v-if="section === 'MI_CUENTA_INFO'">
        <div class="col-12 pb-3">
            <div class="box-aviso">
                <div class="col-12">
                    <div class="row">
                        <div class="col-12">
                            <div class="cerrar">
                                <img
                                    src="/build/img/close.svg"
                                    alt="cerrar"
                                    class="img-fluid"
                                />
                            </div>
                        </div>
                        <div class="col-12">
                            <div class="row align-items-center">
                                <div class="col-12 col-md-1 text-center">
                                    <img
                                        src="/build/img/icon-information.png"
                                        alt="informatición"
                                        class="img-fluid"
                                    />
                                </div>
                                <div
                                    class="col-12 col-md-7 col-lg-8 pt-2 pb-2 pt-md-0 pb-md-0"
                                >
                                    <p>
                                        {{ sectionTitle }}
                                    </p>
                                </div>
                                <div class="col-12 col-md-4 col-lg-3">
                                    <a href="#" class="btn-base btn-blanco"
                                        >Ir al Portal Clientes</a
                                    >
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </template>
    <template v-if="section === 'MI-CUENTA-FAVORITOS'">
        <h1 class="text-left section-title">{{ sectionTitle }}</h1>
        <p class="text-left section-title">
            {{ sectionTitleLargo }} <br class="d-block d-md-none" /><b
                >{{ extra }}
            </b>
        </p>
    </template>
    <template v-if="section === 'MI-CUENTA-GUARDADOS'">
        <h1 class="text-left section-title">{{ sectionTitle }}</h1>
        <p class="text-left section-title">
            {{ sectionTitleLargo }} <br class="d-block d-md-none" /><b
                >{{ extra }}
            </b>
        </p>
    </template>
    <template v-if="section === 'MI-CUENTA'">
        <div class="col-12">
            <div class="row align-items-center">
                <div class="col-12 col-md-9">
                    <h1 class="text-left section-title">{{ sectionTitle }}</h1>
                </div>
                <div class="d-none d-md-block col-md-3">
                    <a
                        type="button"
                        data-toggle="modal"
                        data-target="#exampleModal"
                        class="boton-editar float-right"
                        >Editar
                        <img
                            src="/build/img/editar-icon.svg"
                            alt="icono editar"
                            class="img-fluid"
                    /></a>
                </div>
            </div>
        </div>
    </template>
    <template v-if="section === 'DESTACADOS'">
        <h1 class="text-left section-title">{{ sectionTitle }}</h1>
        <p class="text-left section-title">
            {{ sectionTitleLargo }} <br class="d-block d-md-none" /><b
                >{{ extra }}
            </b>
        </p>
    </template>
    <template v-else-if="section === 'TELEMEDICINA'">
        <h1 class="text-left section-title">{{ sectionTitle }}</h1>
        <p class="text-left section-title">
            {{ sectionTitleLargo }} <br class="d-block d-md-none" /><b
                >{{ extra }}
            </b>
        </p>
    </template>
    <template v-else-if="section === 'BIENESTAR'">
        <h1 class="text-left section-title">{{ sectionTitle }}</h1>
        <p class="text-left section-title">
            <b>{{ sectionTitleLargo }}</b> {{ extra }}
        </p>
    </template>
    <template v-else-if="section === 'BLOG'">
        <h1 class="text-left section-title">{{ sectionTitle }}</h1>
        <p class="text-left section-title">
            {{ sectionTitleLargo }} <b> {{ extra }}</b>
        </p>
    </template>
    <template v-if="section === 'FAVORITOS'">
        <div class="row">
            <div class="col-12 col-lg-7">
                <h1 class="text-left section-title">{{ sectionTitle }}</h1>
            </div>
            <div class="d-none d-lg-block col-md-5 mt-3 text-right">
                <a href="#" class="link--ver__favoritos"
                    >Ver todos mis favoritos
                    <!-- <img src="/build/img/Vector.png" alt="flecha" />-->
                </a>
            </div>
            <div class="col-12">
                <p class="text-left section-title">
                    {{ sectionTitleLargo }} <br class="d-block d-md-none" /><b
                        >{{ extra }}
                    </b>
                </p>
            </div>
        </div>
    </template>
    <template v-if="section === 'TE_PUEDE_INETERESAR'">
        <h1 class="text-left section-title">{{ sectionTitle }}</h1>
        <p class="text-left section-title">
            {{ sectionTitleLargo }} <br class="d-block d-md-none" /><b
                >{{ extra }}
            </b>
        </p>
    </template>
    <template v-if="section === 'ULTIMAS_PUBLICACIONES'">
        <h1 class="text-left section-title">{{ sectionTitle }}</h1>
    </template>
</template>
