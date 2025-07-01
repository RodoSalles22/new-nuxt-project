<template>
<div class="flex flex-col items-center justify-center gap-4 h-screen">
  <h1 class="font-bold text-2xl text-warning">
    Contact Me
  </h1>
  <p class="text-lg text-gray-600">
    Feel free to reach out to me via the form below or by email!
  </p>
  <form class="flex flex-col gap-3 w-full max-w-md bg-white p-6 rounded shadow" @submit.prevent>
    <label class="flex flex-col">
      <span class="mb-1 font-semibold">Name</span>
      <input type="text" class="border rounded px-3 py-2" placeholder="Your name" required>
    </label>
    <label class="flex flex-col">
      <span class="mb-1 font-semibold">Email</span>
      <input type="email" class="border rounded px-3 py-2" placeholder="you@example.com" required>
    </label>
    <label class="flex flex-col">
      <span class="mb-1 font-semibold">Message</span>
      <textarea class="border rounded px-3 py-2" rows="4" placeholder="Your message" required></textarea>
    </label>
    <button type="submit" class="bg-warning text-white font-bold py-2 px-4 rounded hover:bg-warning/80 transition">
      Send Message
    </button>
  </form>
  <div class="text-gray-500 mt-4">
    Or email me at: <a href="mailto:sallesrodolfo0@gmail.com" class="text-warning underline">sallesrodolfo0@gmail.com</a>
  </div>
</div>

</template>