<template>
  <div class="flex flex-col-reverse gap-y-4 text-slate-600">
    <div
      v-for="index in yearsCount"
      :key="index"
      class="flex flex-col-reverse md:flex-col"
    >
      <div class="flex md:space-x-24">
        <div class="hidden md:block bg-blue-600 w-3 rounded-full"/>

        <div class="grow flex space-x-12">
          <div class="relative grow">
            <Card
              :content="content[startYear + index].studies"
              @click="(element) => openCard(element)"
              @close="(element) => closeCard(element)"
            />

            <div
              v-if="content[(startYear + index) - 1] && content[startYear + index].studies.title === content[(startYear + index) - 1].studies.title"
              class="hidden absolute top-full w-full md:block"
            >
              <div class="bg-blue-600 w-2 h-7 my-2 mx-auto rounded-full"/>
            </div>
          </div>

          <div
            v-if="content[startYear + index].job"
            class="relative"
          >
            <Card
              :content="content[startYear + index].job"
              @click="(element) => openCard(element)"
              @close="(element) => closeCard(element)"
            />

            <div
              v-if="content[(startYear + index) - 1].job && content[startYear + index].job.title === content[(startYear + index) - 1].job.title"
              class="hidden absolute top-full w-full md:block"
            >
              <div class="bg-blue-600 w-2 h-7 my-2 mx-auto rounded-full"/>
            </div>
          </div>
        </div>
      </div>


      <div class="mb-8 text-lg flex mt-1 space-x-1 md:mb-0 items-center">
        <div class="bg-blue-600 md:w-3 w-16 h-4 rounded-full"/>
        <div class="ml-1">{{ startYear + index }}</div>
      </div>
    </div>
  </div>
</template>

<script>
import Card from "./Card.vue";

export default {
  components: {Card},
  data() {
    return {
      isOpenCard: false,

      content: {
        2019: {
          studies: {
            title: 'DUT MMI',
            location: 'IUT Angoulême',
            description: 'La filière MMI (Métiers du Multimédia et de l\'Internet) de l\'IUT d\'Angoulême est une formation de niveau bac+2 qui vise à former des professionnels capables de concevoir, de réaliser et de mettre en œuvre des produits et services multimédias interactifs. Elle est ouverte aux bacheliers de toutes les séries, mais particulièrement adaptée aux filières technologiques et professionnelles.\n' +
              '\n' +
              'Au cours de la formation MMI, les étudiants acquièrent des compétences techniques en infographie, en développement web, en audiovisuel, en communication et en marketing. Ils travaillent également sur des projets concrets en collaboration avec des entreprises, des associations ou des institutions, ce qui leur permet de développer leur esprit d\'équipe et leur savoir-faire professionnel.\n' +
              '\n' +
              'L\'IUT d\'Angoulême est réputé pour la qualité de son enseignement et la proximité qu\'il entretient avec le monde professionnel. Les diplômés de la filière MMI sont très recherchés sur le marché du travail et peuvent trouver des débouchés dans des secteurs variés tels que la communication, le marketing, le webdesign, la production audiovisuelle, l\'animation 3D, etc.'
          }
        },
        2020: {
          studies: {
            title: 'DUT MMI',
            location: 'IUT Angoulême',
            description: 'La filière MMI (Métiers du Multimédia et de l\'Internet) de l\'IUT d\'Angoulême est une formation de niveau bac+2 qui vise à former des professionnels capables de concevoir, de réaliser et de mettre en œuvre des produits et services multimédias interactifs. Elle est ouverte aux bacheliers de toutes les séries, mais particulièrement adaptée aux filières technologiques et professionnelles.\n' +
              '\n' +
              'Au cours de la formation MMI, les étudiants acquièrent des compétences techniques en infographie, en développement web, en audiovisuel, en communication et en marketing. Ils travaillent également sur des projets concrets en collaboration avec des entreprises, des associations ou des institutions, ce qui leur permet de développer leur esprit d\'équipe et leur savoir-faire professionnel.\n' +
              '\n' +
              'L\'IUT d\'Angoulême est réputé pour la qualité de son enseignement et la proximité qu\'il entretient avec le monde professionnel. Les diplômés de la filière MMI sont très recherchés sur le marché du travail et peuvent trouver des débouchés dans des secteurs variés tels que la communication, le marketing, le webdesign, la production audiovisuelle, l\'animation 3D, etc.'
          }
        },
        2021: {
          studies: {
            title: 'Licence professionnelle  DAWIN',
            location: 'IUT Bordeaux',
            description: 'L\'IUT de Bordeaux est une institution universitaire située à Bordeaux, en France, qui propose une variété de formations de niveau bac+2 et bac+3 dans différents domaines. L\'une de ses filières les plus réputées est la filière DAWIN.\n' +
              '\n' +
              'La filière DAWIN (Développement d\'Applications Web et Innovation Numérique) de l\'IUT de Bordeaux est une formation de niveau bac+2 qui vise à former des professionnels capables de concevoir, de développer et de mettre en œuvre des applications web innovantes. Elle est ouverte aux bacheliers de toutes les séries, mais particulièrement adaptée aux filières technologiques et professionnelles.\n' +
              '\n' +
              'Au cours de la formation DAWIN, les étudiants acquièrent des compétences techniques en programmation web, en développement mobile, en bases de données, en réseaux informatiques, en sécurité informatique et en gestion de projet. Ils travaillent également sur des projets concrets en collaboration avec des entreprises, des associations ou des institutions, ce qui leur permet de développer leur esprit d\'équipe et leur savoir-faire professionnel.\n' +
              '\n' +
              'L\'IUT de Bordeaux est reconnu pour la qualité de son enseignement et la proximité qu\'il entretient avec le monde professionnel. Les diplômés de la filière DAWIN sont très recherchés sur le marché du travail et peuvent trouver des débouchés dans des secteurs variés tels que l\'informatique, le web, les applications mobiles, le e-commerce, la sécurité informatique, etc.'
          },
          job: {title: 'Puremix', location: 'Bordeaux'}
        },
        2022: {
          studies: {title: 'Master Informatique', location: 'Ynov Bordeaux Campus', description: 'L\'école Ynov est une institution d\'enseignement supérieur privée, spécialisée dans les domaines du design, de la création digitale, de l\'animation, de l\'informatique et des jeux vidéo. Elle est présente dans plusieurs villes de France, dont Bordeaux, Lyon, Nantes, Paris et Toulouse.\n' +
              '\n' +
              'Le Mastère Informatique de l\'école Ynov est une formation de niveau bac+5 qui vise à former des experts en informatique capables de concevoir, de développer et de gérer des projets informatiques complexes. Cette formation est ouverte aux étudiants ayant déjà un diplôme de niveau bac+3 ou bac+4 en informatique, ou ayant une expérience professionnelle équivalente.\n' +
              '\n' +
              'Au cours du Mastère Informatique, les étudiants acquièrent des compétences techniques avancées en programmation, en gestion de projet, en développement de logiciels, en sécurité informatique, en intelligence artificielle et en big data. Ils travaillent également sur des projets concrets en collaboration avec des entreprises, des associations ou des institutions, ce qui leur permet de développer leur esprit d\'équipe et leur savoir-faire professionnel.\n' +
              '\n' +
              'L\'école Ynov est reconnue pour la qualité de son enseignement et la proximité qu\'elle entretient avec le monde professionnel. Les diplômés du Mastère Informatique sont très recherchés sur le marché du travail et peuvent trouver des débouchés dans des secteurs variés tels que la finance, les télécommunications, la sécurité informatique, l\'e-commerce, la santé, etc.'},
          job: {title: 'Puremix', location: 'Bordeaux'}
        },
        2023: {
          studies: {title: 'Master Informatique', location: 'Ynov Bordeaux Campus', description: 'L\'école Ynov est une institution d\'enseignement supérieur privée, spécialisée dans les domaines du design, de la création digitale, de l\'animation, de l\'informatique et des jeux vidéo. Elle est présente dans plusieurs villes de France, dont Bordeaux, Lyon, Nantes, Paris et Toulouse.\n' +
              '\n' +
              'Le Mastère Informatique de l\'école Ynov est une formation de niveau bac+5 qui vise à former des experts en informatique capables de concevoir, de développer et de gérer des projets informatiques complexes. Cette formation est ouverte aux étudiants ayant déjà un diplôme de niveau bac+3 ou bac+4 en informatique, ou ayant une expérience professionnelle équivalente.\n' +
              '\n' +
              'Au cours du Mastère Informatique, les étudiants acquièrent des compétences techniques avancées en programmation, en gestion de projet, en développement de logiciels, en sécurité informatique, en intelligence artificielle et en big data. Ils travaillent également sur des projets concrets en collaboration avec des entreprises, des associations ou des institutions, ce qui leur permet de développer leur esprit d\'équipe et leur savoir-faire professionnel.\n' +
              '\n' +
              'L\'école Ynov est reconnue pour la qualité de son enseignement et la proximité qu\'elle entretient avec le monde professionnel. Les diplômés du Mastère Informatique sont très recherchés sur le marché du travail et peuvent trouver des débouchés dans des secteurs variés tels que la finance, les télécommunications, la sécurité informatique, l\'e-commerce, la santé, etc.'},
          job: {title: 'Puremix', location: 'Bordeaux'},
        },
      }
    }
  },

  props: {
    startYear: Number,
  },

  computed: {
    now() {
      return new Date()
    },

    yearsCount() {
      return this.now.getFullYear() - this.startYear
    }
  },

  methods: {
    openCard(el) {
      this.$el.classList.add('relative')

      el.parentElement.children[1]?.classList.add('md:block')
      el.parentElement.classList.remove('relative')
    },

    closeCard(el) {
      this.$el.classList.remove('relative')

      console.log(el.parentElement)

      el.parentElement.children[1]?.classList.remove('md:block')
      el.parentElement.classList.add('relative')
    }
  }
}
</script>
