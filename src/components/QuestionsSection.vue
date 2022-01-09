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
              <div class="faq-questions-item-content__answer" v-if="!question.isHtml">
                {{ question.answer }}
              </div>
              <div class="faq-questions-item-content__answer" v-else v-html="question.answer">
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
          answer: 'CryptoDynasties collection consists of 10,000 randomly generated and unique 3D characters created from 100 different traits: 25 base types and 75 accessory traits with different levels of rarity.\n\n' +
              'The rarest traits have the lowest % chance of being found among the collection and each trait has a corresponding rarity score.\n\n' +
              'The sum of all the trait scores of one CryptoDynasties NFT marks the total score for the character in our overall Ranking Table.\n\n' +
              'Note: no two NFTs are exactly alike, and each one of them can be officially owned by a single person on the blockchain.',
          img: require('@/assets/img/QuestionsSection/q1img.png')
        },
        {
          question: 'How can I get a "CryptoDynasties" NFT?',
          answer: 'CryptoDynasties NFTs can be purchased exclusively on the Crypto.com/NFT platform. The featured drop will take place on ....\n\n' +
              'To navigate to the Featured Drop simply click on "View Drop" in the first section of this page. \n\n' +
              'The timer on this page will indicate the date and time of the Featured Drop. Since we are using Crypto.com NFT\'s queue system (<a target="_blank" href="https://help.crypto.com/en/articles/5074395-buying-and-selling">What is the queue system?</a>), we advise to queue up early so you won\'t miss your chance to get a queue number.\n\n' +
              'The Featured drop will offer 10,000 CryptoDynasties avatars. Each NFT will have a fixed price and will get you 1 random avatar from the “CryptoDynasties” collection. There\'s a purchasing limit of 5 avatars per person.',
          img: require('@/assets/img/QuestionsSection/q2img.png'),
          isHtml: true
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
