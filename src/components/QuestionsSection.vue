<template>
  <div class="faq-wrapper">
    <div class="container">
      <div class="faq">
        <h3 class="faq__heading">Frequently Asked Questions</h3>
        <div class="faq-questions">
          <div
              class="faq-questions-item"
              v-for="(question, idx) in questions"
              :key="idx"
          >
            <img :src="question.img" alt="qImg" class="faq-questions-item__img"/>
            <div class="faq-questions-item-content">
              <div class="faq-questions-item-content__question">
                {{ question.question }}
              </div>
              <div class="faq-questions-item-content__answer">
                {{ question.answer }}
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "QuestionsSection",
  data() {
    return {
      questions: [
        {
          question: 'What is a "CryptoDynasties" NFT?',
          answer: 'CryptoDynasties collection consists of 10,000 randomly generated and unique 3D characters created from 96 different traits: 20 base types and 76 accessory traits with different levels of rarity.\n' +
              'The rarest traits have the lowest % chance of being found among the collection and each trait has a corresponding rarity score.\n' +
              'The sum of all the trait scores of one CryptoDynasties NFT marks the total score for the character in our overall Ranking Table.\n' +
              'Note: no two NFTs are exactly alike, and each one of them can be officially owned by a single person on the blockchain.',
          img: require('@/assets/img/QuestionsSection/q1img.png')
        },
        {
          question: 'How can I get a "CryptoDynasties" NFT?',
          answer: 'CryptoDynasties NFTs can be exclusively purchased on crypto.com platform. The featured drop will take place once the timer on this page runs out.\n' +
              'To navigate to the Featured Drop simply click on "View Drop" in the first section of this page. \n' +
              'Once the timer runs out on Crypto.com website, simply refresh the page and grab your collectible!\n' +
              'The Featured drop will happen via Mystery Packs. Each pack has a fixed fee and contains 1 random character from the CryptoDynasties collection.',
          img: require('@/assets/img/QuestionsSection/q2img.png')
        },
        {
          question: 'My favorite coin is not in this collection. Are you launching a sequel to the "CryptoDynasties" collection in the future?',
          answer: 'We are sorry to hear that. Let us know which cryptocurrency you\'d like to see in the sequel of this project by filling in this form. Once we have enough votes, the most requested 5 coins will make up the second collection!',
          img: require('@/assets/img/QuestionsSection/q3img.png')
        },
      ]
    }
  }
}
</script>

<style scoped lang="scss">
@import "~@/assets/scss/components/QuestionsSection.scss";
</style>