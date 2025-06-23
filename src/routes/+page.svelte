<script lang="ts">
    import octa from '../lib/images/Octa.png';
    import front from '../lib/images/frontpagebg.png';
    import aboutfw from '../lib/images/aboutfw.png';
    import cg from '../lib/images/Communityguide.png';
    import one from '../lib/images/2 (1).png';
    import two from '../lib/images/2 (2).png';
    import three from '../lib/images/2 (3).png';
    import four from '../lib/images/2 (4).png';
    import five from '../lib/images/1 (1).png';
    import six from '../lib/images/1 (2).png';
    import seven from '../lib/images/1 (3).png';
    import eight from '../lib/images/1 (4).png';
    import rules from '../lib/images/roles.png';
    import guides from '../lib/images/guide.png';

  import { onMount } from 'svelte';
  let isMenuOpen = false;

  const toggleMenu = () => {
    isMenuOpen = !isMenuOpen;
  };

  let activeIndex: number | null = null;

  function toggle(index: number) {
    activeIndex = activeIndex === index ? null : index;
  }

  interface FaqItem {
    question: string;
    answer: string;
  }

  const faqs: FaqItem[] = [
    {
      question: "How do I post anonymously?",
      answer: "When creating a new post, simply select the “Post Anonymously” option before submitting your message. This ensures your identity remains hidden."
    },
    {
      question: "Can I edit or delete my post after submission?",
      answer: "Posts cannot be edited once submitted. However, you can request deletion by contacting the moderators or using the “Report” button on your own post."
    },
    {
      question: "Are all posts visible immediately?",
      answer: "Posts are typically visible immediately unless flagged for moderation. Some posts may undergo review if they breach the platform's guidelines."
    },
    {
      question: "Who can see my posts?",
      answer: "All members of the university community can view your post once it’s live on the Freedom Wall."
    },
    {
      question: "Is my identity protected?",
      answer: "Yes, if you choose to post anonymously, your identity will remain hidden. Even moderators will not be able to see your personal details unless required for serious policy violations."
    },
    {
      question: "How are posts moderated?",
      answer: "Moderators monitor the Freedom Wall to ensure posts adhere to community guidelines. Inappropriate posts will be flagged, reviewed, and potentially removed."
    },
    {
      question: "Can I contact someone directly if I need help?",
      answer: "Yes, you can contact the moderators or support team using the “Contact Us” link in the footer for any issues or questions regarding the platform."
    },
    {
      question: "Why was my post removed?",
      answer: "Posts may be removed if they violate the community guidelines, contain inappropriate content, or are reported by other users. You will be notified if this occurs."
    }
  ];

  

</script>

<nav class="fixed w-full z-[1000] bg-white flex justify-between items-center px-6 py-4 shadow">
  <div class="flex items-center gap-4">
    <a href="#">
      <img src="{octa}" alt="Logo" class="h-14 w-auto" />
    </a>
    <h1 class="text-2xl font-bold font-poppins">O.C.T.A</h1>
  </div>

  <div class="hidden md:flex items-center gap-6">
    <ul class="flex gap-4 text-xs font-bold uppercase font-poppins">
      <li><a href="#" class="hover:text-orange-500 transition">Home</a></li>
      <li><a href="#Freedom Wall" class="hover:text-orange-500 transition">Freedom Wall</a></li>
      <li><a href="#Events" class="hover:text-orange-500 transition">Events</a></li>
      <li><a href="#News" class="hover:text-orange-500 transition">News</a></li>
      <li><a href="#Projects" class="hover:text-orange-500 transition">Projects</a></li>
      <li><a href="#About" class="hover:text-orange-500 transition">About</a></li>
    </ul>
    <button class="relative overflow-hidden border border-orange-300 text-orange-500 font-bold px-3 py-2 rounded-md hover:animate-pulse">
      <span class="relative z-10">Join OCTA</span>
      <span class="absolute top-[-50px] left-[-75px] w-[50px] h-[155px] rotate-[35deg] bg-orange-200/40 z-0 transition-all duration-[550ms] ease-[cubic-bezier(0.19,1,0.22,1)] group-hover:left-[120%]"></span>
    </button>
  </div>

  <div class="md:hidden">
    <button on:click={toggleMenu} aria-label="Toggle Menu">
      <svg xmlns="http://www.w3.org/2000/svg" fill="#ff8c6979" class="h-6 w-6" viewBox="0 0 24 24">
        <path d="M3 6h18M3 12h18M3 18h18" />
      </svg>
    </button>
  </div>
</nav>

<div class={`fixed top-0 right-0 w-[250px] h-screen z-[1001] bg-white/20 backdrop-blur-lg shadow-lg transition-transform duration-300 ease-out ${isMenuOpen ? 'translate-x-0 opacity-100 visible' : 'translate-x-full opacity-0 invisible'}`}>
  <ul class="flex flex-col gap-6 p-6 text-base font-poppins">
    <li class="flex justify-end">
      <button on:click={toggleMenu} aria-label="Close Menu">
        <svg xmlns="http://www.w3.org/2000/svg" fill="#ff8c6979" class="h-6 w-6" viewBox="0 0 24 24">
          <path d="M6 18L18 6M6 6l12 12" />
        </svg>
      </button>
    </li>
    <li><a href="#" on:click={toggleMenu}>Home</a></li>
    <li><a href="#Freedom Wall" on:click={toggleMenu}>Freedom Wall</a></li>
    <li><a href="#Events" on:click={toggleMenu}>Events</a></li>
    <li><a href="#News" on:click={toggleMenu}>News</a></li>
    <li><a href="#Projects" on:click={toggleMenu}>Projects</a></li>
    <li><a href="#About" on:click={toggleMenu}>About</a></li>
    <button class="relative overflow-hidden border border-orange-300 text-orange-500 font-bold px-3 py-2 rounded-md hover:animate-pulse ml-4">
      <span class="relative z-10">Join OCTA</span>
      <span class="absolute top-[-50px] left-[-75px] w-[50px] h-[155px] rotate-[35deg] bg-orange-200/40 z-0 transition-all duration-[550ms] ease-[cubic-bezier(0.19,1,0.22,1)] group-hover:left-[120%]"></span>
    </button>
  </ul>
</div>

<div>

  <div class="relative mt-10 bg-no-repeat bg-cover bg-center min-h-[100vh] flex items-center justify-center" style="background-image: url({front});">
    <div class="relative z-10 flex flex-col items-center justify-center text-center w-full px-4 py-12">
      <h1 class="text-white font-extrabold leading-tight mb-2 text-3xl sm:text-4xl md:text-5xl lg:text-6xl">FREEDOM WALL</h1>
      <p class="text-white font-medium tracking-wide mb-6 text-base sm:text-lg md:text-xl lg:text-2xl">Your Voice. Your Space.</p>
      <div class="flex flex-wrap justify-center gap-4">
        <button class="conbtn text-xs sm:text-sm md:text-base px-3 sm:px-4 md:px-6 py-1.5 sm:py-2 md:py-3">
          Post your thought
        </button>
        <button class="conbtn text-xs sm:text-sm md:text-base px-3 sm:px-4 md:px-6 py-1.5 sm:py-2 md:py-3">
          Browse posts
        </button>
      </div>
    </div>
  </div>


  <div class="conbout w-full max-w-7xl mx-auto rounded-3xl px-4 py-10 flex flex-col gap-y-10 xl:flex-row gap-x-5 lg:gap-y-10 sm:gap-y-10">
    <div class="w-full xl:w-4/12 mb-8 sm:text-center">
      <h1 class="text-3xl sm:text-4xl xl:text-3xl font-bold leading-tight mb-2">
        FREEDOM WALL
      </h1>
      <h3 class="text-base sm:text-lg xl:text-xl font-semibold mb-4">
        Your Voice. Your Space.
      </h3>
      <button class="thoughtbtn text-sm sm:text-base px-4 sm:px-6 py-2 sm:py-3 bg-[#F06336] text-white rounded-md shadow-md hover:bg-[#e3532c] transition">
        Post your thought
      </button>
    </div>

    <div class="w-full xl:w-8/12 text-justify text-sm space-y-4 p-2 sm:text-base md:text-md sm:mt-0">
      <p>
        The OCTA Freedom Wall is a dedicated online space where students of the College of Computer Studies can freely share their thoughts, ideas, and experiences.
      </p>
      <p>
        Whether it's tech innovations, shoutouts, or college life stories, this platform encourages open dialogue in a supportive and respectful environment.
        It's a place to connect, express, and inspire within the OCTA community.
      </p>
    </div>
  </div>


        <!-- svelte-ignore a11y_missing_attribute -->
    <img src="{aboutfw}" class="aboutimg hidden sm:block">

    <img src="{guides}" alt="" class="flex w-[80%] mx-auto block sm:hidden">


    <div class="CYN">
        <div class="CYN-About">
            <h1>Customize Your Notes</h1>
            <p>The OCTA Freedom Wall allows you to express your thoughts and ideas while staying anonymous.<br>
             To make your message stand out, we've curated a variety of note designs just for you!
            </p>
            <button >Post your thought</button>
        </div>
        <div class="px-4 py-6 grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-6 justify-items-center text-center">
          <img src="{one}" alt="icon1" class="w-76 h-auto object-contain">
          <img src="{two}" alt="icon2" class="w-76 h-auto object-contain">
          <img src="{three}" alt="icon3" class="w-76 h-auto object-contain">
          <img src="{four}" alt="icon4" class="w-76 h-auto object-contain">
        </div>
    </div>

  <section class="w-full my-[20vh] px-6 sm:px-12 lg:px-20">
    <div class="flex flex-col lg:flex-row  gap-10">
      <div class="w-full lg:w-1/2 flex flex-col gap-4">
        <div class="flex gap-4">
          <img src="{five}" alt="" class="w-1/2 rounded-lg object-cover hover:scale-105 transition duration-300">
          <img src="{six}" alt="" class="w-1/2 rounded-lg object-cover hover:scale-105 transition duration-300">
        </div>
        <div class="flex gap-4 goup">
          <img src="{seven}" alt="" class="w-1/2 rounded-lg object-cover hover:scale-105 transition duration-300">
          <img src="{eight}" alt="" class="w-1/2 rounded-lg object-cover hover:scale-105 transition duration-300">
        </div>
      </div>

      <div class="w-full lg:w-1/2 max-w-xl p-5">
        <h1 class="text-2xl sm:text-3xl lg:text-4xl font-bold mb-4 mt-[10vh]">Freedom Posts</h1>
        <p class="text-sm sm:text-base text-justify font-medium mb-4">
          The Freedom Posts section is where all contributions from students and teachers are showcased. Whether you're sharing tech insights, personal experiences, or campus-related thoughts, your posts will appear here for others to engage with.
        </p>
        <p class="text-sm sm:text-base text-justify font-medium mb-6">
          It's a space where voices can be heard, ideas can spark discussions, and everyone can connect through shared experiences.
        </p>
        <button class="text-sm sm:text-base sm:px-6 py-2 sm:py-3 conbtn">
          Browse posts
        </button>
      </div>
    </div>
  </section>



<section class="text-center flex flex-col items-center">
  <div class="sm:mx-auto items-center">
    <h1 class="w-full text-[#F06336] text-[clamp(1.5rem,3vw,2.25rem)] font-bold text-center px-7 py-4 my-7 bg-white rounded-3xl shadow-2xl drop-shadow-2xl sm:px-[15vh] md:px-[30vh]">
      Community Guidelines
    </h1>
  </div>
  <img src="{cg}" alt="" class="rounded-3xl shadow-md shade drop-shadow-xl w-[70%] p-7 hidden sm:block"/>
  <img src="{rules}" alt="" class="rounded-3xl shadow-md shade drop-shadow-xl block sm:hidden p-7 w-[70%]">
</section>

  <div class="wrapper px-4 md:px-20">
  <h1 class="text-2xl md:text-3xl font-bold text-center mb-6">FAQs</h1>
  {#each faqs as faq, index}
    <div class="faq">
      <button
        class="accordion {activeIndex === index ? 'active' : ''}"
        on:click={() => toggle(index)}
      >
        {faq.question}
        <i class="fa-solid fa-chevron-down"></i>
      </button>
      <div class="pannel" style="display: {activeIndex === index ? 'block' : 'none'}">
        <p>{faq.answer}</p>
      </div>
    </div>
  {/each}
  </div>

</div>


<footer class="bg-zinc-800 text-white font-poppins py-10 px-4 md:px-10 pb-10 sm:pb-7">
  <div class="max-w-7xl mx-auto">
    <div class="grid grid-cols-1 md:grid-cols-3 gap-10 border-b border-white pb-6 text-center md:text-left">
      <div class="flex flex-col items-center md:items-start">
        <div class="flex items-center mb-4">
          <img src="{octa}" alt="OCTA Logo" class="w-12 h-12" />
          <h2 class="ml-2 font-bold text-xl">O.C.T.A</h2>
        </div>
        <p class="text-sm leading-relaxed max-w-sm p-3">
          Here at O.C.T.A, we like to unite our voices, embrace diversity, and drive forward the
          progress of computing and technology advancement. We want to create an inclusive,
          supportive community where everyone feels heard.
        </p>
      </div>

      <div class="flex flex-col items-center">
        <h3 class="font-bold text-lg mb-3">Navigation</h3>
        <ul class="space-y-1 text-sm pl-0 md:pl-[30vh]">
          <li><a href="#" class="hover:underline">Freedom Wall</a></li>
          <li><a href="#" class="hover:underline">Events</a></li>
          <li><a href="#" class="hover:underline">News</a></li>
          <li><a href="#" class="hover:underline">Projects</a></li>
          <li><a href="#" class="hover:underline">About</a></li>
        </ul>
      </div>

      <div class="flex flex-col items-center md:items-end">
        <h3 class="font-bold text-lg mb-3">Get In Touch</h3>
        <div class="flex space-x-4 text-2xl">
          <a href="#"><i class="fa-brands fa-github"></i></a>
          <a href="#"><i class="fa-brands fa-facebook"></i></a>
          <a href="#"><i class="fa-brands fa-x-twitter"></i></a>
        </div>
      </div>
    </div>

    <div class="flex flex-col sm:flex-row justify-center gap-4 text-sm text-center pt-6 sm:pt-7">
      <h4 class="hover:underline cursor-pointer pt-2">Terms And Conditions</h4>
      <h4 class="hover:underline cursor-pointer pt-2">Privacy Policy</h4>
    </div>
  </div>
</footer>


<style>
    @import '../lib/Css/style.css';
    @import '../lib/Css/nav.css';
</style>
