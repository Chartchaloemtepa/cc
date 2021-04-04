<template>
  <div>
    <div class="text-gray-600 body-font">
      <div class="row py-20">
        <div class="row px-5 flex flex-wrap w-full">
          <p
            class="text-center p-5 lg:w-1/2 w-full leading-relaxed text-gray-500"
          >
            Whatever cardigan tote bag tumblr hexagon brooklyn asymmetrical
            gentrify, subway tile poke farm-to-table. Franzen you probably
            haven't heard of them man bun deep jianbing selfies heirloom prism
            food truck ugh squid celiac humblebrag.
          </p>
          <img src="../assets/spa.jpg" alt="" class="w-1/3 px-10" />
        </div>
        <div class="inline-grid grid-cols-4 gap-x-4 px-20 py-20">
          <div class="" v-for="pa in packages" :key="pa.id.toString()">
            <div class="bg-gray-100">
              <img :src="pa.img" alt="" />
              {{ pa.name }}
              <h3 class="text-indigo-500 text-xs font-medium title-font pt-10">
                SUBTITLE
              </h3>
              <h2 class="text-lg text-gray-900 font-medium title-font mb-4">
                {{ pa.title }}
              </h2>
              <p class="leading-relaxed text-base">
                {{ pa.subtitle }}
              </p>
              <div class="py-5 p-5">
                <form class="flex" @submit.prevent="add(pa)">
                  <button
                    type="submit"
                    class="w-1/3 rounded-xl bg-green-600 text-white"
                  >
                    add
                  </button>
                </form>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div>
      <div class="flex flex-col text-base text-gray-700 md:text-lg text-center">
        <h2>Shopping Cart</h2>
      </div>
      <table style="margin-left: 500px">
        <thead class="flex px-10 text-center">
          <td class="p-5">#</td>
          <td class="p-5">Hour</td>
          <td class="p-5">Price</td>
          <td class="p-5">Product Name</td>
        </thead>
        <tbody>
          <tr v-for="(d, idx) in cart" :key="d.id.toString()" class="flex p-5">
            <td class="p-5">{{ idx + 1 }}</td>
            <td class="flex flex-inline">
              <div class="flex flex-2 pt-5 p-3">{{ d.quantity }}</div>
            </td>
            <td class="p-5">{{ d.price }}</td>
            <td class="p-5">{{ d.title }}</td>
          </tr>
          <tr>
            <td>
              <h4 class="">Total : {{ total }}</h4>
            </td>
            <td></td>
            <td></td>
            <td>
              <button
                class="flex flex-col bg-yellow-700 p-3 rounded"
                @click="buy"
              >
                Buy
              </button>
            </td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</template>

<script lang="js">
  export default {
    name: "Cart",
    props: {
      msg: String,
    },
    data() {
      return {
        ticket: {
          products: null,
          total: 0,
        },
        packages: [
          {
            id: 1,
            img: require('~/assets/magic-four-hand-package.webp'),
            title: "Magical Four Hand Package",
            subtitle:"Perhaps our most transformational experience, this treatment begins with Oriental Foot Reflexology and a KIN Secret Charm Silky Hair Treatment given at the same time. Then you encounter the luxurious Oasis Four Hand Massage, a signature treatment. During this choreographed tandem massage, two therapists delicately work with all four hands in synchronization to produce waves of enjoyment. Your whole body will feel lighter and bursting with life after this over-the-top-experience.",
            price: 10.99,
            cart: false,
            quantity: 1,
          },
          {
            id: 2,
            img: require('@/assets/sabai-stone-massage.webp'),
            title: "Sabai Stone Massage",
            subtitle:"Take a stepping-stone to a better you. First, an Aromatherapy and Swedish Massage applied with smooth, round, heated basalt stones relieve tired and sore muscle. Then Sabai Stones are positioned at strategic locations on the body to melt away muscle knots and tension and to relieve stress. Additional stones are applied to massage away pain and improve the flow of life energy. Results are dramatic: you walk away feeling reborn.",
            price: 14.99,
            cart: false,
            quantity: 1,
          },
          {
            id: 3,
            img: require("@/assets/ayuraved-package.webp"),
            title: "Ayuraved Package",
            subtitle:"This unique spa package begins with the dripping of warm oil on the forehead which is believed to invigorate and sooth the senses and the mind. It is followed by a thorough scalp massage. Next, a traditional East Indian Style warm-oil massage reduces tension, swelling and helps improve sleep. Many find this two-hour treatment helps prevents illness and promotes healing and wellness by balancing the body, mind and spirit.",
            price: 19.99,
            cart: false,
            quantity: 1,
          },
          {
            id: 4,
            img: require("@/assets/seaside-sensation.webp"),
            title: "PETSIN Pineapple Design Pet Costume",
            subtitle:"This therapy combines our seaside spas’ most popular treatments. First, enjoy a healthful Thai Herbal Steam then take a quick dip in our Cool Pool. Next, receive a cleansing KIN Cool Ocean Breeze Body Scrub and the Aloe Vera & Lavender Body Wrap. Your seaside pampering sensation is complete with a two-hour King of Oasis Signature Massage and a Detoxifying Facial. Many call this their, “Best spa therapy eeeveer!”",
            price: 104.99,
            cart: false,
            quantity: 1,
          },
        ],
        cart: [],
        fields: ["#", "remove", "name", "quantity", "price"],
      }; // data return
    },
    methods: {
      add(pa) {
        this.cart.push(pa);

      },
      buy() {
        alert("Purchase Complete");
      },
    },
    computed: {
      total() {
        let t = 0;
        for (let index = 0; index < this.cart.length; index++) {
          t += this.cart[index].price * this.cart[index].quantity;
        }
        return t.toFixed(2);
      },
    },
  }
</script>
<style>