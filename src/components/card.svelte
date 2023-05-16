<script>
  export let card = { content: "", id: "" };
</script>

<div
  class="max-w-md mx-auto m-6 bg-white rounded-xl shadow-md overflow-hidden md:max-w-2xl"
>
  <div class="md:flex">
    <div class="md:shrink-0">
      <img
        class="h-48 w-full object-cover md:h-full md:w-48"
        src={Image}
        alt="content"
      />
    </div>
    <div class="p-8">
      <div
        class="uppercase tracking-wide text-sm text-indigo-500 font-semibold"
      >
        ID: {card.id}
      </div>
      <a
        href="/"
        class="block mt-1 text-lg leading-tight font-medium text-black hover:underline"
        >User Input</a
      >
      <p class="mt-2 text-slate-500">{card.content}</p>
    </div>
  </div>
</div>
