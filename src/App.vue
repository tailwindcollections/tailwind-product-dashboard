<script setup>
import OverviewIcon from "./icons/overview.svg";
import ShoppingBagIcon from "./icons/shopping-bag.svg";
import GraphIcon from "./icons/graph.svg";
import CalendarIcon from "./icons/calendar.svg";
import WalletIcon from "./icons/wallet.svg";
import FileIcon from "./icons/file.svg";
import ChatIcon from "./icons/chat.svg";
import GroupChatIcon from "./icons/group-chat.svg";
import SettingsIcon from "./icons/settings.svg";
import LogoutIcon from "./icons/logout.svg";
import PlusIcon from "./icons/plus.svg";
import LayersIcon from "./icons/layers.svg";
import DraftIcon from "./icons/draft.svg";
import InvisibleIcon from "./icons/invisible.svg";
import RejectedIcon from "./icons/rejected.svg";
import MailIcon from "./icons/mail.svg";
import FilterIcon from "./icons/filter.svg";
import FigmaIcon from "./icons/figma.svg";
import SketchIcon from "./icons/sketch.svg";
import AIIcon from "./icons/ai.svg";
import PencilIcon from "./icons/pencil.svg";
import TrashIcon from "./icons/trash.svg";
import ChevronLeftIcon from "./icons/chevron-left.svg";
import ChevronRightIcon from "./icons/chevron-right.svg";

const sidebar = [
  [
    { name: "Overview", icon: OverviewIcon },
    { name: "Products", icon: ShoppingBagIcon },
    { name: "Analytics", icon: GraphIcon },
    { name: "Schedule", icon: CalendarIcon },
    { name: "Payout", icon: WalletIcon },
    { name: "Statements", icon: FileIcon },
  ],
  [
    { name: "Help", icon: ChatIcon },
    { name: "Community", icon: GroupChatIcon },
    { name: "Settings", icon: SettingsIcon },
    { name: "Logout", icon: LogoutIcon },
  ],
];

const status = [
  { name: "Published", icon: LayersIcon },
  { name: "Draft", icon: DraftIcon },
  { name: "Hidden", icon: InvisibleIcon },
  { name: "Rejected", icon: RejectedIcon },
  { name: "Under Review", icon: MailIcon },
];

const products = [
  {
    name: "Organic Landing page",
    category: "Web Design",
    imageUrl: "/img/organic-landing-page.png",
    price: 20,
    downloaded: 793,
    rating: 4.9,
    platformIcons: [FigmaIcon, SketchIcon],
    createdAt: "12/01/22",
  },
  {
    name: "Traffic Landing page",
    category: "Web Design",
    imageUrl: "/img/traffic-landing-page.png",
    price: 24,
    downloaded: 34,
    rating: 4.4,
    platformIcons: [FigmaIcon, AIIcon],
    createdAt: "10/01/22",
  },
  {
    name: "POS Dashboard",
    category: "Web Design",
    imageUrl: "/img/pos-dashboard.png",
    price: 16,
    downloaded: 896,
    rating: 4.6,
    platformIcons: [FigmaIcon, SketchIcon],
    createdAt: "01/01/22",
  },
  {
    name: "Gallery page",
    category: "Web Design",
    imageUrl: "/img/gallery-page.png",
    price: 38,
    downloaded: 194,
    rating: 4.6,
    platformIcons: [FigmaIcon, SketchIcon],
    createdAt: "04/01/22",
  },
  {
    name: "WFH Landing page",
    category: "Web Design",
    imageUrl: "/img/wfh-landing-page.png",
    price: 22,
    downloaded: 404,
    rating: 4.3,
    platformIcons: [FigmaIcon, SketchIcon],
    createdAt: "12/12/21",
  },
];
</script>

<template>
  <div class="w-full min-h-screen font-sans text-gray-900 bg-gray-50 flex">
    <aside class="py-6 px-10 w-64 border-r border-gray-200">
      <img src="/img/logo.png" alt="" class="w-28" />
      <ul v-for="group in sidebar" class="flex flex-col gap-y-6 pt-20">
        <li v-for="item in group">
          <a
            href="#"
            class="flex gap-x-4 items-center py-2 text-gray-500 hover:text-indigo-600 group"
          >
            <span
              class="absolute w-1.5 h-8 bg-indigo-600 rounded-r-full left-0 scale-y-0 -translate-x-full group-hover:scale-y-100 group-hover:translate-x-0 transition-transform ease-in-out"
            />
            <Component :is="item.icon" class="w-6 h-6 fill-current" />
            <span>{{ item.name }}</span>
          </a>
        </li>
      </ul>
    </aside>

    <main class="flex-1 pb-8">
      <div class="flex items-center justify-between py-7 px-10">
        <div>
          <h1 class="text-2xl font-semibold leading-relaxed text-gray-800">Products</h1>
          <p class="text-sm font-medium text-gray-500">
            Let's grow to your business! Create your product and upload here
          </p>
        </div>
        <button
          class="inline-flex gap-x-2 items-center py-2.5 px-6 text-white bg-indigo-600 rounded-xl hover:bg-indigo-700 focus:outline-none focus:ring-2 focus:ring-indigo-500 focus:ring-offset-1"
        >
          <PlusIcon class="w-6 h-6 fill-current" />
          <span class="text-sm font-semibold tracking-wide">Create Item</span>
        </button>
      </div>

      <ul class="flex gap-x-24 items-center px-4 border-y border-gray-200">
        <li v-for="item in status">
          <button
            class="flex gap-x-2 items-center py-5 px-6 text-gray-500 hover:text-indigo-600 relative group"
          >
            <Component :is="item.icon" class="w-6 h-6 fill-current" />
            <span class="font-medium"> {{ item.name }} </span>
            <span
              class="absolute w-full h-0.5 left-3 bg-indigo-600 rounded bottom-0 scale-x-0 group-hover:scale-x-100 transition-transform ease-in-out"
            />
          </button>
        </li>
      </ul>

      <table class="w-full border-b border-gray-200">
        <thead>
          <tr class="text-sm font-medium text-gray-700 border-b border-gray-200">
            <td class="pl-10">
              <div class="flex items-center gap-x-4">
                <input
                  type="checkbox"
                  class="w-6 h-6 text-indigo-600 rounded-md border-gray-300"
                  indeterminate="indeterminate"
                />
                <span>Product Name</span>
              </div>
            </td>
            <td class="py-4 px-4 text-center">Pricing</td>
            <td class="py-4 px-4 text-center">Downloaded</td>
            <td class="py-4 px-4 text-center">Rating</td>
            <td class="py-4 px-4 text-center">Platforms</td>
            <td class="py-4 pr-10 pl-4 text-center">
              <FilterIcon class="w-6 h-6 fill-current" />
            </td>
          </tr>
        </thead>
        <tbody>
          <tr
            v-for="product in products"
            class="hover:bg-gray-100 transition-colors group"
          >
            <td class="flex gap-x-4 items-center py-4 pl-10">
              <input
                type="checkbox"
                class="w-6 h-6 text-indigo-600 rounded-md border-gray-300"
              />
              <img
                :src="product.imageUrl"
                alt=""
                class="w-40 aspect-[3/2] rounded-lg object-cover object-top border border-gray-200"
              />
              <div>
                <a href="#" class="text-lg font-semibold text-gray-700">
                  {{ product.name }}
                </a>
                <div class="font-medium text-gray-400">{{ product.category }}</div>
              </div>
            </td>
            <td class="font-medium text-center">${{ product.price }}</td>
            <td class="font-medium text-center">{{ product.downloaded }}</td>
            <td class="text-center">
              <span class="font-medium">{{ product.rating }}</span>
              <span class="text-gray-400">/5</span>
            </td>
            <td>
              <div class="flex gap-x-2 justify-center items-center">
                <a
                  href="#"
                  v-for="icon in product.platformIcons"
                  class="p-2 bg-gray-200 rounded-md hover:bg-gray-300"
                >
                  <Component :is="icon" class="w-6 h-6" />
                </a>
              </div>
            </td>
            <td>
              <span class="inline-block w-20 group-hover:hidden">
                {{ product.createdAt }}
              </span>
              <div
                class="hidden group-hover:flex group-hover:w-20 group-hover:items-center group-hover:text-gray-500 group-hover:gap-x-2"
              >
                <button class="p-2 hover:rounded-md hover:bg-gray-200">
                  <PencilIcon class="w-6 h-6 fill-current" />
                </button>
                <button class="p-2 hover:rounded-md hover:bg-gray-200">
                  <TrashIcon class="w-6 h-6 fill-current" />
                </button>
              </div>
            </td>
          </tr>
        </tbody>
      </table>

      <div class="flex gap-x-2 justify-center pt-8">
        <button class="flex justify-center items-center w-8 h-8">
          <ChevronLeftIcon
            class="w-6 h-6 to-gray-800 stroke-current hover:text-indigo-600"
          />
        </button>
        <button
          v-for="i in 6"
          class="flex items-center justify-center w-8 h-8 font-medium rounded-full"
          :class="
            i === 1 ? 'bg-gray-800 text-white' : 'text-gray-400 hover:text-indigo-600'
          "
        >
          {{ i }}
        </button>
        <button class="flex justify-center items-center w-8 h-8">
          <ChevronRightIcon
            class="w-6 h-6 to-gray-800 stroke-current hover:text-indigo-600"
          />
        </button>
      </div>
    </main>
  </div>
</template>
