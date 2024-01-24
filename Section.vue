<script setup>
import { ref, onMounted } from "vue";
import Card4Favoritos from "../Cards/Card4Favoritos.vue";
import Card6Col from "@/Components/Cards/Card6Col.vue";
import Card4Col from "@/Components/Cards/Card4Col.vue";
import TituloSection from "@/Components/Sections/TituloSection.vue";
import Card6ColImagen from "@/Components/Cards/Card6ColImagen.vue";
import Card4ColFecha from "@/Components/Cards/Card4ColFecha.vue";
import Card3PubCol from "@/Components/Cards/Card3PubCol.vue";
import Card_mi_cuenta from "@/Components/Cards/Card-mi-cuenta.vue";

const props = defineProps({
    section: {
        type: String,
        required: true,
    },
    estilo: {
        default: null,
        type: String,
        required: true,
    },
    objetocard: {
        default: null,
        type: Object,
    },
    objetocard_2: {
        default: null,
        type: Object,
    },
    tituloSection: {
        default: null,
        type: Object,
    },
    user: {
        type: Object,
        default: null,
    },
    verMas: {
        type: Boolean,
        default: false,
    },
});

const cardsFavoritosRef = ref(null);
onMounted(() => {
    cardsFavoritosRef.value.scrollToCards(cardsFavoritosRef.value);
});
</script>
<template>
    <div :class="[estilo]">
        <div class="container">
            <template v-if="section === 'MI-CUENTA_PRINCIPAL'">
                <div class="col-12 mb-5">
                    <TituloSection
                        v-for="(tit, index) in tituloSection"
                        :key="`${index}${tit.title}`"
                        :extra="tit.extra"
                        :sectionTitleLargo="tit.descripcion"
                        :sectionTitle="tit.title"
                        :section="section"
                        :favoritos="tit.favoritos"
                        :guardados="tit.guardados"
                        :cambiar_clave="tit.cambiar_clave"
                    />
                </div>
            </template>
            <template v-if="section === 'MI_CUENTA_INFO'">
                <div class="col-12">
                    <TituloSection
                        v-for="(tit, index) in tituloSection"
                        :key="`${index}${tit.title}`"
                        :sectionTitle="tit.title"
                        :sectionTitleLargo="tit.descripcion"
                        :section="section"
                    />
                </div>
            </template>
            <template v-if="section === 'MI-CUENTA'">
                <div class="col-12">
                    <TituloSection
                        v-for="(tit, index) in tituloSection"
                        :key="`${index}${tit.title}`"
                        :extra="tit.extra"
                        :sectionTitleLargo="tit.descripcion"
                        :sectionTitle="tit.title"
                        :section="section"
                    />
                </div>

                <div class="col-12">
                    <div
                        class="d-flex flex-column flex-md-row box-user__profile justify-content-center"
                    >
                        <Card_mi_cuenta
                            v-for="(data, index) in props.objetocard"
                            :key="`${index}${data.title}`"
                            :iconoSrc_user="data.iconoSrc_user"
                            :iconoSrc_rut="data.iconoSrc_rut"
                            :iconoSrc_email="data.iconoSrc_email"
                            :iconoSrc_fecha="data.iconoSrc_fecha"
                            :iconoSrc_comuna="data.iconoSrc_comuna"
                            :iconoSrc_telefono="data.iconoSrc_telefono"
                            :imageSrc="data.imageSrc"
                            :user="user"
                        />
                    </div>
                </div>
            </template>
            <template v-if="section === 'MI-CUENTA-FAVORITOS'">
                <div class="col-12 mt-5 p-3">
                    <TituloSection
                        v-for="(tit, index) in tituloSection"
                        :key="`${index}${tit.title}`"
                        :sectionTitle="tit.title"
                        :section="section"
                    />
                </div>
                <div
                    id="cards-favoritos"
                    ref="cardsFavoritosRef"
                    class="mr-3 ml-3 d-flex flex-row align-items-center justify-content-between"
                >
                    <Card4Col
                        v-for="(data, index) in props.objetocard_2"
                        :key="`${index}${data.title}`"
                        :title="data.title"
                        :descripcion="data.descripcion"
                        :estado="data.estado"
                        :categoria="data.categoria"
                        :imageSrc="data.imageSrc"
                    />
                </div>

                <div v-if="verMas">
                    <div class="container">
                        <div class="col-12">
                            <div class="row">
                                <div class="col-12">
                                    <div class="grid--content mt-4">
                                        <div class="column--wrapper">
                                            <Card4Favoritos
                                                v-for="(
                                                    data, index
                                                ) in props.objetocard.slice(
                                                    0,
                                                    cardsVisibles
                                                )"
                                                :key="`${index}${data.title}`"
                                                :title="data.title"
                                                :descripcion="data.descripcion"
                                                :estado="data.estado"
                                                :categoria="data.categoria"
                                                :imageSrc="data.imageSrc"
                                            />
                                        </div>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                    <!-- PAGINADOR -->
                    <div class="col-12">
                        <nav class="pagination justify-content-center">
                            <ul>
                                <li>
                                    <a href="#0">
                                        <img
                                            src="/build/img/Arrow_Left_Blue_Outline_RGB.png"
                                            alt=""
                                        />
                                    </a>
                                </li>
                                <li class="active">
                                    <a href="#1">1</a>
                                </li>
                                <li class="">
                                    <a href="#2">2</a>
                                </li>
                                <li class="">
                                    <a href="#3">3</a>
                                </li>
                                <li class="">
                                    <a href="#4">4</a>
                                </li>
                                <li class="">
                                    <a href="#5">5</a>
                                </li>
                                <li>
                                    <a href="#6">
                                        <img
                                            src="/build/img/Arrow_Right_Blue_Outline_RGB.png"
                                            alt=""
                                        />
                                    </a>
                                </li>
                            </ul>
                        </nav>
                    </div>
                    <!-- PAGINADOR -->
                </div>
                <div class="col-12">
                    <div
                        id="botonVerMasFavoritos"
                        class="btn-base btn-azul mr-auto mt-5 mb-3"
                        @click="
                            verMas = !verMas;
                            cardsVisibles = verMas
                                ? 7
                                : props.objetocard.length;
                        "
                    >
                        <span
                            id="texto-boton-varFavoritos"
                            v-bind:innerText="verMas ? 'Ver menos' : 'Ver más'"
                        ></span
                        ><img
                            src=" /build/img/FLECHA-BOTON.svg "
                            alt="flecha"
                            class="img-fluid"
                            v-bind:style="{
                                transform: verMas
                                    ? 'rotate(180deg)'
                                    : 'rotate(0deg)',
                            }"
                        />
                    </div>
                </div>
            </template>
            <template v-if="section === 'MI-CUENTA-GUARDADOS'">
                <div class="col-12 mt-5 p-3">
                    <TituloSection
                        v-for="(tit, index) in tituloSection"
                        :key="`${index}${tit.title}`"
                        :sectionTitle="tit.title"
                        :section="section"
                    />
                </div>
                <div
                    class="mr-3 ml-3 d-flex flex-row align-items-center justify-content-between"
                >
                    <Card4Col
                        v-for="(data, index) in props.objetocard_2"
                        :key="`${index}${data.title}`"
                        :title="data.title"
                        :descripcion="data.descripcion"
                        :estado="data.estado"
                        :categoria="data.categoria"
                        :imageSrc="data.imageSrc"
                    />
                </div>

                <div v-if="verMas">
                    <div class="container">
                        <div class="col-12">
                            <div class="row">
                                <div class="col-12">
                                    <div class="grid--content mt-4">
                                        <div class="column--wrapper">
                                            <Card4Favoritos
                                                v-for="(
                                                    data, index
                                                ) in props.objetocard.slice(
                                                    0,
                                                    cardsVisibles
                                                )"
                                                :key="`${index}${data.title}`"
                                                :title="data.title"
                                                :descripcion="data.descripcion"
                                                :estado="data.estado"
                                                :categoria="data.categoria"
                                                :imageSrc="data.imageSrc"
                                            />
                                        </div>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                    <!-- PAGINADOR -->
                    <div class="col-12">
                        <nav class="pagination justify-content-center">
                            <ul>
                                <li>
                                    <a href="#0">
                                        <img
                                            src="/build/img/Arrow_Left_Blue_Outline_RGB.png"
                                            alt=""
                                        />
                                    </a>
                                </li>
                                <li class="active">
                                    <a href="#1">1</a>
                                </li>
                                <li class="">
                                    <a href="#2">2</a>
                                </li>
                                <li class="">
                                    <a href="#3">3</a>
                                </li>
                                <li class="">
                                    <a href="#4">4</a>
                                </li>
                                <li class="">
                                    <a href="#5">5</a>
                                </li>
                                <li>
                                    <a href="#6">
                                        <img
                                            src="/build/img/Arrow_Right_Blue_Outline_RGB.png"
                                            alt=""
                                        />
                                    </a>
                                </li>
                            </ul>
                        </nav>
                    </div>
                    <!-- PAGINADOR -->
                </div>
                <div class="col-12">
                    <div
                        id="botonVerMasFavoritos"
                        class="btn-base btn-azul mr-auto mt-5 mb-3"
                        @click="
                            verMas = !verMas;
                            cardsVisibles = verMas
                                ? 7
                                : props.objetocard.length;
                        "
                    >
                        <span
                            id="texto-boton-varFavoritos"
                            v-bind:innerText="verMas ? 'Ver menos' : 'Ver más'"
                        ></span
                        ><img
                            src=" /build/img/FLECHA-BOTON.svg "
                            alt="flecha"
                            class="img-fluid"
                            v-bind:style="{
                                transform: verMas
                                    ? 'rotate(180deg)'
                                    : 'rotate(0deg)',
                            }"
                        />
                    </div>
                </div>
            </template>
            <template v-if="section === 'DESTACADOS'">
                <div class="col-12">
                    <TituloSection
                        v-for="(tit, index) in tituloSection"
                        :key="`${index}${tit.title}`"
                        :extra="tit.extra"
                        :sectionTitleLargo="tit.descripcion"
                        :sectionTitle="tit.title"
                        :section="section"
                    />
                </div>
                <div class="col-12">
                    <div
                        class="d-flex flex-column flex-md-row align-items-center justify-content-between"
                    >
                        <Card4Col
                            v-for="(data, index) in props.objetocard"
                            :key="`${index}${data.title}`"
                            :title="data.title"
                            :descripcion="data.descripcion"
                            :estado="data.estado"
                            :categoria="data.categoria"
                            :imageSrc="data.imageSrc"
                        />
                    </div>
                </div>
            </template>
            <template v-else-if="section === 'TELEMEDICINA'">
                <div class="col-12 pb-4">
                    <TituloSection
                        v-for="(tit, index) in tituloSection"
                        :key="`${index}${tit.title}`"
                        :extra="tit.extra"
                        :sectionTitleLargo="tit.descripcion"
                        :sectionTitle="tit.title"
                        :section="section"
                    />
                </div>
                <div class="col-12">
                    <div class="row">
                        <Card6Col
                            v-for="(data, index) in props.objetocard"
                            :key="`${index}${data.title}`"
                            :title="data.title"
                            :descripcion="data.descripcion"
                            :estado="data.estado"
                            :categoria="data.categoria"
                            :imageSrc="data.imageSrc"
                        />
                    </div>
                </div>
            </template>
            <template v-else-if="section === 'BIENESTAR'">
                <div class="col-12 pb-4">
                    <TituloSection
                        v-for="(tit, index) in tituloSection"
                        :key="`${index}${tit.title}`"
                        :extra="tit.extra"
                        :sectionTitleLargo="tit.descripcion"
                        :sectionTitle="tit.title"
                        :section="section"
                    />
                </div>
                <div class="col-12">
                    <div class="row">
                        <Card6ColImagen
                            v-for="(data, index) in props.objetocard"
                            :key="`${index}${data.title}`"
                            :title="data.title"
                            :descripcion="data.descripcion"
                            :estado="data.estado"
                            :disponibilidad="data.disponibilidad"
                            :categoria="data.categoria"
                            :imageSrc="data.imageSrc"
                        />
                    </div>
                </div>
            </template>
            <template v-else-if="section === 'BLOG'">
                <div class="col-12">
                    <TituloSection
                        v-for="(tit, index) in tituloSection"
                        :key="`${index}${tit.title}`"
                        :extra="tit.extra"
                        :sectionTitleLargo="tit.descripcion"
                        :sectionTitle="tit.title"
                        :section="section"
                    />
                </div>
                <div class="col-12">
                    <div
                        class="d-flex flex-column flex-md-row align-items-center justify-content-between"
                    >
                        <Card4ColFecha
                            v-for="(data, index) in props.objetocard"
                            :key="`${index}${data.title}`"
                            :title="data.title"
                            :descripcion="data.descripcion"
                            :fecha="data.fecha"
                            :categoria="data.categoria"
                            :imageSrc="data.imageSrc"
                        />
                    </div>
                </div>
            </template>
            <template v-if="section === 'FAVORITOS'">
                <div class="col-12">
                    <TituloSection
                        v-for="(tit, index) in tituloSection"
                        :key="`${index}${tit.title}`"
                        :extra="tit.extra"
                        :sectionTitleLargo="tit.descripcion"
                        :sectionTitle="tit.title"
                        :section="section"
                    />
                </div>

                <div class="section-destacados sections">
                    <div class="container">
                        <div class="col-12">
                            <div class="row">
                                <div class="col-12">
                                    <div class="grid--content mt-4">
                                        <div class="column--wrapper">
                                            <Card4Favoritos
                                                v-for="(
                                                    data, index
                                                ) in props.objetocard"
                                                :key="`${index}${data.title}`"
                                                :title="data.title"
                                                :descripcion="data.descripcion"
                                                :estado="data.estado"
                                                :categoria="data.categoria"
                                                :imageSrc="data.imageSrc"
                                            />
                                        </div>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </template>
            <template v-if="section === 'TE_PUEDE_INETERESAR'">
                <div class="col-12">
                    <TituloSection
                        v-for="(tit, index) in tituloSection"
                        :key="`${index}${tit.title}`"
                        :extra="tit.extra"
                        :sectionTitleLargo="tit.descripcion"
                        :sectionTitle="tit.title"
                        :section="section"
                    />
                </div>
                <div class="col-12">
                    <div
                        class="d-flex flex-column flex-md-row align-items-center justify-content-between"
                    >
                        <Card4Col
                            v-for="(data, index) in props.objetocard"
                            :key="`${index}${data.title}`"
                            :title="data.title"
                            :descripcion="data.descripcion"
                            :estado="data.estado"
                            :categoria="data.categoria"
                            :imageSrc="data.imageSrc"
                        />
                    </div>
                </div>
            </template>
            <template v-if="section === 'ULTIMAS_PUBLICACIONES'">
                <div class="col-12">
                    <TituloSection
                        v-for="(tit, index) in tituloSection"
                        :key="`${index}${tit.title}`"
                        :extra="tit.extra"
                        :sectionTitleLargo="tit.descripcion"
                        :sectionTitle="tit.title"
                        :section="section"
                    />
                </div>
                <div class="col-12">
                    <div
                        class="d-flex flex-column flex-md-row align-items-center justify-content-between"
                    >
                        <Card3PubCol
                            v-for="(data, index) in props.objetocard"
                            :key="`${index}${data.title}`"
                            :title="data.title"
                            :descripcion="data.descripcion"
                            :estado="data.estado"
                            :categoria="data.categoria"
                            :imageSrc="data.imageSrc"
                        />
                    </div>
                </div>
            </template>
        </div>
    </div>
</template>
