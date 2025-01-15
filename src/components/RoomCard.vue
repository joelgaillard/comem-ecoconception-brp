<template>
    <div class="card-container" :class="[isFlipped ? 'back' : 'front']"
        :style="!isFlipped ? { backgroundImage: `url(${img})` } : {}">
        <h4 :class="[isFlipped ? 'back' : 'front']">{{ name }}</h4>
        <div v-if="isFlipped" class="text-container">
            <p><span class="label">Superficie:</span> {{ area }} m2</p>
            <p><span class="label">Vue:</span> {{ view }}</p>
            <p><span class="label">Exposition:</span> {{ exposure }}</p>
            <p><span class="label">Balcon:</span> {{ balcony ? 'Oui' : 'Non' }}</p>
        </div>
        <div :class="['button-container', isFlipped ? 'back' : 'front']">
            <div v-if="!isFlipped" class="rotate-icon"></div>
            <Button v-if="!isFlipped" class="info-button" msg="Informations" @click="goToRoom" />
            <inline-svg :src="RotateIcon" :class="['rotate-icon', isFlipped ? 'back' : 'front']" @click="flipCard" />
        </div>
    </div>
</template>

<script setup>
import { ref } from 'vue';
import { useRouter } from 'vue-router';
import Button from './Button.vue';
import InlineSvg from 'vue-inline-svg';
import RotateIcon from '/src/assets/svg/rotate-icon.svg';

const props = defineProps({
  id: {
    type: Number,
    required: true,
  },
  type: {
    type: String,
    required: true,
  },
  name: {
    type: String,
    required: true,
  },
  img: {
    type: String,
    required: true,
  },
  area: {
    type: Number,
    required: true,
  },
  view: {
    type: String,
    required: true,
  },
  exposure: {
    type: String,
    required: true,
  },
  balcony: {
    type: Boolean,
    default: false,
  }
});

const isFlipped = ref(props.type !== 'room');
const router = useRouter();

function flipCard() {
  isFlipped.value = !isFlipped.value;
}

function goToRoom() {
  router.push(`/rooms/${props.id}`);
}

</script>

<style scoped>
.card-container {
    display: flex;
    flex-direction: column;
    padding: 10%;
    aspect-ratio: 5/6;
    justify-content: space-between;
    background-color: var(--cararra);
    background-size: cover;
    background-position: center;
}

.card-container .front {
    align-items: center;
    color: var(--whitesmoke);
    text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.5);
    text-align: center;
}

.card-container .back {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
}

.button-container {
    width: 100%;
    display: flex;
    justify-content: space-between;
    flex-direction: row;
}

.rotate-icon {
    cursor: pointer;
    align-self: flex-end;
    width: 2rem;
}

.front .rotate-icon {
    fill: var(--whitesmoke);
}

.front .rotate-icon:hover {
    fill: var(--woodsmoke);
}

.back .rotate-icon:hover {
    fill: var(--whitesmoke);
}

.text-container {
    display: flex;
    flex-direction: column;
}

.label {
    font-family: var(--antarctica-semibold);
}

</style>