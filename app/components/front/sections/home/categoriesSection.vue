<script setup lang="ts">
import PageSection from "../../ui/pageSection.vue";
import Slider from "../../ui/slider.vue";
import CategoryCard from "../../ui/categoryCard.vue";

const title = "Browse talent by category"
const subTitle = "Get some Inspirations from 1800+ skills"
const link = {to: '#', text: 'All Categories'}
const categories = [
  {
    name: "Development & IT",
    icon: "/img/dev_cat_icon.svg",
    subCategories: [
      {
        group: "Développement Web",
        items: ["Frontend", "Backend", "Full-stack", "CMS & e-commerce", "Web performance & optimisation"],
      },
      {
        group: "Développement Mobile",
        items: ["Applications iOS", "Applications Android", "Cross-platform", "CMS & e-commerce", "Progressive Web Apps"],
      },
      {
        group: "DevOps & Infrastructure",
        items: ["CI/CD & automatisation", "Conteneurisation", "Cloud", "Infrastructure as Code"],
      },
      {
        group: "Tests & Qualité",
        items: ["Tests automatisés", "QA manuelle", "Tests de performance & charge", "Audit de code"],
      },
      {
        group: "Architecture & Ingénierie logicielle",
        items: ["Architecture logicielle", "APIs & intégrations", "Sécurité applicative", "Refonte & migration de systèmes"],
      },
      {
        group: "Data & Intelligence Artificielle",
        items: ["Data engineering & pipelines", "Analyse de données & visualisation", "Machine Learning / Deep Learning", "NLP & traitement du langage"],
      },
      {
        group: "Cybersécurité",
        items: ["Pentesting & audits de sécurité", "Sécurité réseau & cloud", "Conformité (RGPD, ISO 27001)", "Sécurisation d’applications web"],
      },
      {
        group: "Administration Systèmes & Réseaux",
        items: ["Administration Linux / Windows Server", "Virtualisation & hyperviseurs", "Monitoring & alerting", "Support technique & maintenance"],
      },
      {
        group: "Conseil & Architecture IT",
        items: ["Audit technique", "Transformation digitale", "Choix technologiques & roadmap", "Coaching technique & mentoring"],
      },
    ]
  },
  {
    name: "Design & Creative",
    icon: "/img/design_icon.svg",
    subCategories: [
      {
        group: "Design graphique",
        items: ["Identité visuelle & branding", "Création de logos", "Design d’affiches & flyers", "Design de packaging", "Illustration vectorielle & dessin", "Design éditorial"],
      },
      {
        group: "UI/UX Design",
        items: ["Design d’interfaces web & mobile", "Prototypage & wireframes", "Design system & composants UI", "Accessibilité & ergonomie", "Tests utilisateurs & audits UX"],
      },
      {
        group: "Design de contenu digital",
        items: ["Création de visuels pour réseaux sociaux", "Templates pour newsletters & emailings", "Miniatures YouTube, bannières, carrousels", "Présentations", "GIFs & visuels animés"],
      },
      {
        group: "Direction artistique & conception créative",
        items: ["Direction artistique de marque", "Moodboards & storytelling visuel", "Création de chartes graphiques", "Refonte visuelle & harmonisation", "Création de concepts créatifs"],
      },
      {
        group: "Design produit & industriel",
        items: ["Design d’objets & packaging", "Maquettes 3D & rendus", "Design d’interfaces embarquées", "Design mobilier & accessoires"],
      },
      {
        group: "Motion design & animation",
        items: ["Animation 2D/3D", "Vidéos explicatives animées", "Génériques & intros/outros", "Transitions & effets visuels", "Animation typographique"],
      },
      {
        group: "Photographie & retouche",
        items: ["Retouche photo & colorimétrie", "Photomontage & effets spéciaux", "Packshots produits", "Photographie lifestyle / mode / événementielle"],
      },
      {
        group: "Création de contenu visuel",
        items: ["Infographies & data visualisation", "Storyboards & planches narratives", "Design de CV & portfolios", "Création de mockups"],
      },
    ]
  },
  {
    name: "Digital Marketing",
    icon: "/img/marketing_icon.svg",
    subCategories: [
      {
        group: "Publicité en ligne",
        items: ["Google Ads", "Meta Ads", "TikTok Ads / Snapchat Ads", "LinkedIn Ads / Twitter Ads", "YouTube Ads & vidéo sponsorisée", "Retargeting & remarketing"],
      },
      {
        group: "SEO & Référencement naturel",
        items: ["Audit SEO technique", "Optimisation on-page", "Netlinking & backlinks", "SEO local", "SEO e-commerce", "Rédaction SEO"],
      },
      {
        group: "Email marketing & automation",
        items: ["Création de newsletters", "Segmentation & scénarios automatisés", "Intégration avec CRM", "A/B testing & taux de conversion", "Copywriting d’emails"],
      },
      {
        group: "Social Media & Community Management",
        items: ["Stratégie de contenu social", "Création de calendriers éditoriaux", "Animation de communautés", "Modération & gestion de crise", "Reporting & analytics sociaux"],
      },
      {
        group: "Stratégie marketing & branding",
        items: ["Positionnement & storytelling de marque", "Stratégie d’acquisition & funnel marketing", "Analyse concurrentielle & veille", "Growth marketing & hacking", "Plan marketing digital"],
      },
      {
        group: "Marketing e-commerce",
        items: ["Optimisation de fiches produits", "Stratégie de conversion (CRO)", "Upsell / cross-sell / bundles", "Analyse de parcours client", "Intégration analytics & tracking"],
      },
      {
        group: "Web analytics & tracking",
        items: ["Google Analytics (GA4)", "Tag Manager & événements personnalisés", "Suivi des conversions & KPIs", "Tableaux de bord", "Attribution & analyse multi-touch"],
      },
      {
        group: "Tests & optimisation",
        items: ["A/B testing & multivarié", "Heatmaps & enregistrements", "UX analytics & feedback utilisateurs", "Optimisation de landing pages"],
      },
      {
        group: "Rédaction & contenu marketing",
        items: ["Copywriting & storytelling", "Création de landing pages", "Scripts vidéo & publicités", "Contenu pour réseaux sociaux", "Blogging & inbound marketing"],
      },
    ]
  },
  {
    name: "Writing & Translation",
    icon: "/img/translation_icon.svg",
    subCategories: [
      {
        group: "Rédaction de contenu",
        items: ["Articles de blog & SEO", "Rédaction web", "Rédaction e-commerce", "Rédaction technique", "Rédaction académique & recherche", "Ghostwriting"],
      },
      {
        group: "Copywriting & Marketing",
        items: ["Textes publicitaires & slogans", "Rédaction de newsletters & emails marketing", "Scripts vidéo & spots publicitaires", "Pages de vente & funnels", "Storytelling de marque", "Optimisation conversion"],
      },
      {
        group: "Édition & Correction",
        items: ["Relecture orthographique & grammaticale", "Correction stylistique", "Édition académique", "Mise en page & formatage", "Vérification de cohérence terminologique"],
      },
      {
        group: "Traduction",
        items: ["Traduction générale", "Traduction technique", "Traduction marketing & publicitaire", "Localisation de sites web & logiciels", "Traduction audiovisuelle"],
      },
      {
        group: "Transcription & Adaptation",
        items: ["Transcription audio/vidéo", "Sous-titrage multilingue", "Adaptation culturelle & localisation", "Transcription juridique ou médicale"],
      },
      {
        group: "Création littéraire & artistique",
        items: ["Écriture créative", "Scénarios & dramaturgie", "Scripts pour podcasts ou vidéos", "Contenu narratif pour jeux vidéo"],
      },
      {
        group: "Spécialisations linguistiques",
        items: ["Linguistique & terminologie", "Adaptation multilingue pour UX/UI", "Traduction assermentée", "Services multilingues pour entreprises"],
      },
    ]
  },
  {
    name: "Music & Audio",
    icon: "/img/audio_icon.svg",
    subCategories: [
      {
        group: "Composition & Production musicale",
        items: ["Composition originale", "Beatmaking & production hip-hop/EDM", "Musique de film, publicité & jeux vidéo", "Arrangement & orchestration", "Jingles & identités sonores"],
      },
      {
        group: "Voix & Enregistrement vocal",
        items: ["Voix-off", "Doublage & localisation audio", "Podcasts & narration audio", "Chant & interprétation", "Audiobooks & storytelling"],
      },
      {
        group: "Mixage & Mastering",
        items: ["Mixage multipiste", "Mastering professionnel", "Correction de tonalité & auto-tune", "Nettoyage audio", "Optimisation pour plateformes"],
      },
      {
        group: "Sound Design & Effets sonores",
        items: ["Création d’effets sonores", "Sound design pour jeux vidéo", "Foley & bruitages cinéma", "Design sonore pour interfaces", "Bibliothèques sonores personnalisées"],
      },
      {
        group: "Podcast & Production audio digitale",
        items: ["Création & montage de podcasts", "Édition & habillage sonore", "Génériques & transitions audio", "Optimisation voix & compression", "Distribution & publication"],
      },
      {
        group: "Musique live & interprétation",
        items: ["Enregistrement d’instruments", "Performances live enregistrées", "Musiciens de session", "Groupes & orchestres virtuels"],
      },
      {
        group: "Conseil & Stratégie audio",
        items: ["Direction artistique musicale", "Stratégie sonore de marque", "Coaching vocal & musical", "Consulting en production audio"],
      },
    ]
  },
  {
    name: "Video & Animation",
    icon: "/img/video_icon.svg",
    subCategories: [
      {
        group: "Production vidéo",
        items: ["Tournage & réalisation", "Vidéos promotionnelles & marketing", "Interviews & témoignages", "Clips musicaux", "Vidéos institutionnelles & documentaires", "Captation live & streaming"],
      },
      {
        group: "Montage & post-production",
        items: ["Montage vidéo", "Étalonnage & correction colorimétrique", "Effets visuels", "Motion tracking & compositing", "Sous-titrage & incrustations", "Optimisation pour plateformes"],
      },
      {
        group: "Animation 2D & 3D",
        items: ["Motion design", "Animation 2D", "Animation 3D", "Infographies animées", "Génériques & transitions animées"],
      },
      {
        group: "Effets spéciaux & VFX",
        items: ["Compositing & incrustation fond vert", "Simulation", "CGI pour films & jeux vidéo", "Intégration d’éléments 3D dans des vidéos réelles"],
      },
      {
        group: "Vidéo marketing & publicité",
        items: ["Vidéos explicatives", "Publicités digitales & spots TV", "Vidéos pour réseaux sociaux", "Vidéos de lancement produit", "Storytelling visuel de marque"],
      },
      {
        group: "Animation pour jeux vidéo",
        items: ["Cinématiques & cutscenes", "Animation de personnages", "FX pour gameplay", "Assets animés pour UI/UX"],
      },
      {
        group: "Conseil & direction artistique vidéo",
        items: ["Storyboarding & scénarisation", "Direction artistique & moodboards", "Stratégie de contenu vidéo", "Coaching en production audiovisuelle"],
      },
    ]
  },
  {
    name: "Engineering & Architecture",
    icon: "/img/ing_cat_icon.svg",
    subCategories: [
      {
        group: "Architecture & Design architectural",
        items: ["Conception de bâtiments résidentiels", "Architecture commerciale & industrielle", "Urbanisme & aménagement", "Rénovation & réhabilitation", "Dessins techniques & plans 2D/3D", "Visualisation architecturale"],
      },
      {
        group: "Ingénierie civile & construction",
        items: ["Génie civil", "Calculs de résistance & stabilité", "Plans de construction & devis", "Gestion de projet de chantier", "BIM (Building Information Modeling)"],
      },
      {
        group: "Ingénierie mécanique",
        items: ["Conception de pièces & machines", "CAO/DAO (SolidWorks, AutoCAD, CATIA)", "Prototypage & impression 3D", "Simulation mécanique", "Maintenance industrielle"],
      },
      {
        group: "Ingénierie électrique & électronique",
        items: ["Schémas électriques & circuits imprimés (PCB)", "Automatisation & robotique", "Systèmes embarqués", "Énergie renouvelable & solaire", "Domotique & smart home"],
      },
      {
        group: "Ingénierie environnemental",
        items: ["Études d’impact environnemental", "Gestion de l’eau & assainissement", "Énergies durables", "Conception éco-responsable", "Optimisation énergétique des bâtiments"],
      },
      {
        group: "Ingénierie chimique & matériaux",
        items: ["Process industriels & chimie appliquée", "Conception d’installations chimiques", "Études de matériaux & composites", "Sécurité industrielle & normes"],
      },
      {
        group: "Ingénierie spécialisée",
        items: ["Aéronautique & spatial", "Ingénierie automobile", "Ingénierie maritime", "Ingénierie biomédicale", "Nanotechnologies"],
      },
      {
        group: "Services techniques & support",
        items: ["Dessin technique & modélisation 2D/3D", "Plans d’ingénierie détaillés", "Conversion de fichiers CAD", "Documentation technique", "Conseil & expertise technique"],
      },
    ]
  },
  {
    name: "Finance & Accounting",
    icon: "/img/finance_cat_icon.svg",
    subCategories: [
      {
        group: "Comptabilité & tenue de livres",
        items: ["Comptabilité générale", "Tenue de livres", "Comptabilité analytique", "Gestion des factures & paiements", "Clôture mensuelle & annuelle"],
      },
      {
        group: "Fiscalité & conformité",
        items: ["Déclarations fiscales", "TVA & taxes locales", "Optimisation fiscale", "Conformité réglementaire", "Audit fisca"],
      },
      {
        group: "Finance d’entreprise",
        items: ["Prévisions financières & budgets", "Gestion de trésorerie", "Analyse financière & reporting", "Tableaux de bord financiers", "Business plans & projections", "Contrôle de gestion"],
      },
      {
        group: "Investissements & gestion d’actifs",
        items: ["Analyse de portefeuilles", "Gestion d’investissements", "Études de rentabilité", "Conseil en stratégie financière", "Évaluation d’entreprises"],
      },
      {
        group: "Paie & administration RH",
        items: ["Gestion de la paie", "Déclarations sociales", "Avantages & primes", "Conformité RH", "Externalisation paie"],
      },
      {
        group: "Audit & conseil",
        items: ["Audit comptable & financier", "Due diligence", "Conseil en restructuration", "Optimisation des coûts", "Stratégie de financement"],
      },
      {
        group: "Services spécialisés",
        items: ["Comptabilité internationale", "Conversion de devises & consolidation", "Normes IFRS / US GAAP", "Gestion multi-entités", "Services pour ONG & associations"],
      },
    ]
  },
]
</script>

<template>
  <page-section :title="title" :sub-title="subTitle" :link="link">
    <!--slider>
      <category-card v-for="category in categories" :sub-categories="category.subCategories.map(sc => sc.group)"
                     :name="category.name" :nb-skills="category.subCategories.length" :logo="category.icon"/>
    </slider-->
  </page-section>
</template>

<style scoped>

</style>