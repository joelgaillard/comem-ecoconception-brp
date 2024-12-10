<script setup>
import InlineSvg from 'vue-inline-svg';
import LogoLeadersClub from '/src/assets/svg/logo_leaders-club.svg'
import LogoLeadingHotels from '/src/assets/svg/logo_leading-hotels.svg'
import LogoSwissDeluxeHotels from '/src/assets/svg/swiss-deluxe-hotels-logo.svg'
import LogoSwisstainable from '/src/assets/svg/Swisstainable-Logo.svg'
import LogoFondationSandoz from '/src/assets/svg/logo_fondation_sandoz.svg'
</script>

<template>
    <footer>
        <div>
            <div class="footer-adress">
                <p>Hôtel Beau-Rivage Palace<br>Chemin de Beau-Rivage 21<br>1006 Lausanne</p>
                <div>
                    <a href="tel:+41216133333">+41 21 613 33 33</a>
                    <a href="mailto:info@brp.ch">info@brp.ch</a>
                </div>
            </div>
            <div class="footer-vertical-line-separator footer-mobile"></div>
            <div class="footer-labels">
                <inline-svg :src="LogoLeadersClub" width="9rem" height="6.25rem" class="footer-label" />
                <inline-svg :src="LogoLeadingHotels" width="9rem" height="6.25rem"  class="footer-label"  />
                <inline-svg :src="LogoSwissDeluxeHotels" width="9rem" height="6.25rem" class="footer-label"  />
                <inline-svg :src="LogoSwisstainable" width="9rem" height="6.25rem" class="footer-label"  />
            </div>
        </div>
        <div>
            <div class="footer-vertical-line-separator"></div>
        </div>
        <div>
            <div class="footer-foundation-logo">
                <inline-svg :src="LogoFondationSandoz" width="300" height="150" />
            </div>
            <div class="footer-foundation-hotels-links">
                <a href="https://www.lausanne-palace.ch/">Lausanne Palace</a>
                <a href="https://www.angleterre-residence.ch/">Angleterre & Résidence</a>
                <a href="https://www.chateaudouchy.ch/">Château d'Ouchy</a>
                <a href="https://www.palafitte.ch/">Hôtel Palafitte</a>
                <a href="https://www.riffelalp.com/">Riffelalp 2222m</a>
            </div>
        </div>
        <div>
            <div class="footer-vertical-line-separator"></div>
        </div>
        <div>
            <div class="footer-menu">
                <a class="legend" href="#">Galerie</a>
                <a class="legend" href="#">Carrière</a>
                <a class="legend" href="#">Le développement durable</a>
                <a class="legend" href="#">Presse</a>
                <a class="legend" href="#">Finance</a>
                <a class="legend" href="#">Plan du site</a>
                <a class="legend" href="#">Impressum</a>
                <a class="legend" href="#">Politique de confidentialité</a>
                <a class="legend" href="#">Gestion des données</a>
            </div>
            <div class="footer-copyright legend">
                <span>© Beau-Rivage Palace 2024</span>
            </div>
        </div>
    </footer>
</template>

<style>
footer {
    background-color: var(--cararra);
    display: flex;
    width: 100dvw;
    padding: 0rem 2.5rem;
    flex-direction: column;
    align-items: center;
    gap: 1.875rem;
}
footer>div {
    display: flex;
    padding: 0.625rem 2.5rem;
    justify-content: space-between;
    align-items: center;
    align-self: stretch;
}
.footer-adress {
    display: flex;
    padding: 0.625rem;
    align-items: felx-start;
    gap: 5rem;
    align-self: stretch;
}
.footer-adress a {
    display: block;
}
.footer-labels {
    display: flex;
    padding: 10px 0px;
    align-items: flex-end;
    gap: 40px;
}
.footer-label {
    fill: var(--woodsmoke);
    color: var(--woodsmoke);
    max-width: 20%;
    max-height: 6.25rem;
    width: auto;
    height: auto;
}
.footer-vertical-line-separator {
    width: 100%;
    height: 1px;
    padding: 0;
    margin: 0;
    background-color: var(--woodsmoke);
    opacity: 0.2;
}
.footer-foundation-logo img {
    max-width: 40%;
    max-height: 6.25rem;
    width: auto;
    height: auto;
}
.footer-foundation-hotels-links {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    align-items: center;
    gap: 1rem 2rem;
}
.footer-menu {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    align-items: center;
    gap: 0.5rem 2rem;
}
.footer-mobile {
    display: none;
}

@media (max-width : 1400px) {
    footer {
        padding: 0;
    }
    footer>div {
        flex-direction: column;
        gap: 1.875rem;
    }
    .footer-adress {
        justify-content: center;
    }
    .footer-mobile {
        display: block;
    }
}

@media (max-width : 600px) {
    .footer-adress {
        flex-direction: column;
        gap: 1rem;
    }
}

</style>