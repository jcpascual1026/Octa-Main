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
  <!-- Logo Section -->
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

    <div class="container mt-10" style="background-image: url({front})">
        <h1 class="text-[4vw] text-white pb-1 font-bold"> FREEDOM WALL</h1>
        <p class="text-white text-xl tracking-widest pb-10"> Your Voice. Your Space.</p>
        <button class="conbtn" >Post your thought</button>
        <button class="conbtn">Browse posts</button>
    </div>

    <div class="">
        <div class="conbout mt-20">
            <h1 class="text-4xl pb-5 w-[40%] font-extrabold">FREEDOM WALL</h1>
            <h3 class="font-bold w-[40%]">Your Voice. Your Space.</h3>
            <button class="thoughtbtn"> Post your thought</button>

            <div class="right">
                <p class="max-w-[80vh] w-11/12 justify-center ">The OCTA Freedom Wall is a dedicated online space where students
                of the College of Computer Studies can freely share their thoughts,
                ideas, and experiences. 
                </p>
             <br>
                <p class="w-[75vh]">Whether it's tech innovations, shoutouts, or college life stories, this platform encourages open dialogue in a supportive and respectful environment.
                 It's a place to connect, express, and inspire within the OCTA community.
                </p>
            </div>
           
        </div>
        <!-- svelte-ignore a11y_missing_attribute -->
        <img src="{aboutfw}" class="aboutimg">
    </div>

    <div class="CYN">
        <div class="CYN-About">
            <h1>Customize Your Notes</h1>
            <p>The OCTA Freedom Wall allows you to express your thoughts and ideas while staying anonymous.<br>
             To make your message stand out, we've curated a variety of note designs just for you!
            </p>
            <button >Post your thought</button>
        </div>
        <div class="cynimg">
          <img src="{one}" alt="">
          <img src="{two}" alt="">
          <img src="{three}" alt="">
          <img src="{four}" alt="">
        </div>
    </div>

   <div class="freedompost">
        <div class="fdexample">
          <div class="fdexampleTop flex">
            <img src="{five}" alt="" class="fdexampleimg">
            <img src="{six}" alt="" class="fdexampleimg">
          </div>
          <div class="fdexampleBot flex">
            <img src="{seven}" alt="" class="fdexampleimg">
            <img src="{eight}" alt="" class="fdexampleimg">
          </div>
        </div>
        <div class="freedompostContainer">
            <h1 class="text-4xl font-bold">Freedom Posts</h1>
            <p class="text-sm pt-5 font-bold">
                The Freedom Posts section is where all contributions from students and teachers are showcased.
                Whether you're sharing tech insights, personal experiences,
                or campus-related thoughts, your posts will appear here for others to engage with. 
            </p>
            <br>
            <p class="text-sm font-bold">
                It's a space where voices can be heard, ideas can spark discussions, and everyone can connect through shared experiences.
            </p>
            
            <button class="conbtn">Browse posts</button>
        </div>
    </div>

<section class="text-center flex flex-col items-center">
  <div class="mx-[30vh]">
    <h1 class="text-[#F06336] text-[4.6vh] my-[5vh] mb-[10vh] px-[40vh] py-5 rounded-xl shadow-md shade drop-shadow-xl">
      Community Guidelines
    </h1>
  </div>
  <img src="{cg}" alt="" class="rounded-3xl shadow-md shade drop-shadow-xl w-[70%] p-7"/>
</section>

  <div class="wrapper">
  <h1>FAQs</h1>
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

<footer class="bg-zinc-800 text-white font-poppins pt-10 pb-4 px-[20vh]">
  <div class="max-w-6xl mx-auto px-6">
    <!-- Grid layout: 3 columns -->
    <div class="grid grid-cols-1 md:grid-cols-3 gap-10 border-b border-white pb-6 text-center md:text-left">
      
      <!-- Left: About -->
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

      <!-- Center: Navigation -->
      <div class="flex flex-col items-center">
        <h3 class="font-bold text-lg mb-3">Navigation</h3>
        <ul class="space-y-1 text-sm pl-[30vh]">
          <li><a href="#" class="hover:underline">Freedom Wall</a></li>
          <li><a href="#" class="hover:underline">Events</a></li>
          <li><a href="#" class="hover:underline">News</a></li>
          <li><a href="#" class="hover:underline">Projects</a></li>
          <li><a href="#" class="hover:underline">About</a></li>
        </ul>
      </div>

      <!-- Right: Socials -->
      <div class="flex flex-col items-center md:items-end">
        <h3 class="font-bold text-lg mb-3">Get In Touch</h3>
        <div class="flex space-x-4 text-2xl">
          <a href="#"><i class="fa-brands fa-github"></i></a>
          <a href="#"><i class="fa-brands fa-facebook"></i></a>
          <a href="#"><i class="fa-brands fa-x-twitter"></i></a>
        </div>
      </div>
    </div>

    <!-- Bottom: Terms -->
    <div class="flex justify-center gap-8 py-4 text-sm">
      <h4 class="hover:underline cursor-pointer">Terms And Conditions</h4>
      <h4 class="hover:underline cursor-pointer">Privacy Policy</h4>
    </div>
  </div>
</footer>


<style>
    @import '../lib/Css/style.css';
    @import '../lib/Css/nav.css';
</style>
