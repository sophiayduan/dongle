        <script lang="ts">
            import { onMount } from 'svelte';

            import port from '$lib/assets/port.svg';
            import star from '$lib/assets/star.svg';
            import flower from '$lib/assets/flower.svg';

            import comu from '$lib/assets/comu.webp';
            import usbhub from '$lib/assets/usb-hub.webp';
            import picoducky from '$lib/assets/picoducky.webp';

            onMount(() => {
                let cancelled = false;
                let cleanup: (() => void) | undefined;

                (async () => {
                    const { gsap } = await import('gsap');
                    const { ScrambleTextPlugin } = await import('gsap/all');
                    if (cancelled) return;

                    gsap.registerPlugin(ScrambleTextPlugin) 
                    
                    const borders = document.querySelectorAll('borders')
                    gsap.to(borders, {
                        duration:5,
                        ease: "none",
                        delay: 0.2,
                        scrambleText: "XXXXXXXXXXXX"
                    });

                })(); 


                return () => {
                    cancelled = true;
                    cleanup?.();
                };


            });

        </script>

        <main class="w-screen h-full flex flex-col gap-4 relative">
            <section class="hero lg:w-[80%] mx-auto lg:h-screen flex flex-col py-14 lg:pt-24 p-6 ">
                <div class="flex flex-col items-start justify-center gap-2 h-fit px-4">

                    <h1 class="text-[16vw] font-bold font-hk leading-20 sm:leading-30 lg:leading-50 flex items-center">
                        <span class="leading-20 lg:leading-60">D</span>
                        <div class="xl:mx-1 grid grid-cols-1 grid-rows-1 place-items-center group">
                            <span class="col-start-1 row-start-1 leading-20 lg:leading-30">O</span>
                            <img src={star} alt="" class="w-12 lg:w-20 col-start-1 row-start-1 animate-[spin_8s_linear_infinite]" />
                        </div>
                        <span class="leading-20 lg:leading-30">N</span>
                        <span class="leading-20 lg:leading-30">G</span>
                        <span class="leading-20 lg:leading-30">L</span>
                        <span class="leading-20 lg:leading-30">E</span>
                    </h1>

                    <h3 class="text-2xl lg:text-3xl font-geist font-medium lg:ml-1 sm:mt-6">Design a PCB that plugs into your laptop, get prizes!</h3>
                    <p class="text-lg sm:text-xl">//: Ends August 27th 12:00PM EST</p>
                    <div class="flex items-center w-full gap-3 lg:gap-4">
                    <p class="hidden lg:block lg:text-lg max-w-xl text-light-blue opacity-80 leading-tight">Dongles are a piece of hardware that when plugged in a laptop (or tv/phone/etc!) port add a feature. </p>
                    <a href="/guide" class="mt-4 lg:mt-0 lg:ml-auto mb-4 p-2 lg:p-4 bg-yellow font-hk text-xl sm:text-3xl lg:text-5xl text-black hover:bg-light-blue transition-all duration-100 hover:cursor-pointer w-fit rounded-sm">
                        <span>GUIDES</span>
                    </a>

                    <a href="https://forms.hackclub.com/dongle" class="mb-4 p-2 lg:p-4 mt-4 lg:mt-0  bg-red font-hk text-xl sm:text-3xl lg:text-5xl flex gap-4 items-center hover:bg-black hover:cursor-pointer rounded-sm transition-all duration-200 group">
                        <span>SUBMIT</span>
                        <div class="bg-white p-1 aspect-square rounded-sm">
                            <svg class="w-6 sm:w-8" viewBox="0 0 33 33" fill="none" xmlns="http://www.w3.org/2000/svg">
                            <path d="M2.5 29.7628L29.7628 2.5M2.5 2.5H29.7628V29.7628" stroke="#1E1E1E" stroke-width="5" stroke-linecap="round" stroke-linejoin="round"/>
                            </svg>
                        </div>
                    </a>                     
                    </div>
                </div>
                <img src={port} alt="" class="w-full px-4 lg:px-0" />
            </section>

            <section class="w-full h-full px-6">
            <div class="lg:w-[80%] lg:mx-auto p-4 mt-8">
                 <p class="p-8 sm:p-4"> <b>Design a PCB that plugs into your laptop directly or via a cable!</b> It should be fun, functional, and/or add flair to your laptop. <i>Not sure where to start? Checkout the <a class="underline font-bold" href="/guide">USB LED Dongle Guide</a> to make a computer control led board (It's beginner friendly!) and join us at <a href="https://hackclub.enterprise.slack.com/archives/C0BT2TGD6BS" target="_blank" class="underline">#dongle</a>  on Slack! </i>
                </p>
                <br/> 
                <p>Time working on your project should be tracked within a <span class="rounded-xs px-1 py-px mx-1 bg-yellow font-bold text-black">JOURNAL.md</span>
                in your code repository, and be sure to <span class="rounded-xs px-1 py-px mx-1 bg-yellow font-bold text-black">include a BOM</span> in the README.md!
                </p>
            </div>
           
            <div class="mt-8 w-full h-full p-4 bg-white py-8">
             <div class='lg:w-[80%] lg:mx-auto'>
                <h3 class="text-blue font-hk text-4xl">PROJECT IDEAS</h3>
                <p class="text-blue">Check out other dongle-related Hack Clubber projects!</p>

                <div class="mt-4 flex-col sm:flex-row flex items-center w-full border-4 border-blue overflow-hidden">
                    <div
                        class="w-full sm:w-1/3 h-70 sm:h-50 md:h-80 lg:h-100 bg-cover bg-center"
                        style={`background-image: url(${comu})`}
                    ></div>

                    <div
                        class="w-full sm:w-1/3 h-70 sm:h-50 md:h-80 lg:h-100 bg-contain bg-no-repeat bg-center border-y-4 sm:border-y-0 sm:border-x-4  border-blue"
                        style={`background-image: url(${usbhub});`}
                    ></div>

                    <div class="w-full sm:w-1/3 h-70 sm:h-50 md:h-80 lg:h-100">
                        <img
                            src={picoducky}
                            alt="rudy's usb hub"
                            class="w-full h-full object-cover"
                        />
                    </div>
                </div>

                <div class="mt-2 grid grid-cols-3 text-blue leading-snug text-sm gap-8 text-center opacity-0 sm:opacity-100">
                    <p class="">By @Cyao, an 18-year-old from France!</p>
                    <p class="">By @Hiral, a 17-year-old from India!</p>
                    <p class="">By @Rudy, a teen from Canada!</p>

                </div>
             <div class="my-12 bg-white h-fit text-black">
            <div class="flex gap-4 items-center">
                <h3 class="text-black font-hk text-4xl">PRIZES</h3>
                <img src={flower} alt="" class="inline h-10" />
            </div>
            <h4 class="mt-4 bg-yellow p-1 px-4 rounded-sm font-bold w-fit">TIER 1: Hack Club Stickers</h4>
            <li class="ml-6 mt-2">Hand-picked HC stickers - I'll ship you some special ones!</li>

            <h4 class="mt-4 bg-yellow p-1 px-4 rounded-sm font-bold w-fit">TIER 2: 16 GB Flash Drive</h4>
            <li class="ml-6 mt-2">Unique, high-quality projects will receive this on top of Hack Club stickers! If you're unsure your project will qualify, send it in <a href="https://hackclub.enterprise.slack.com/archives/C0BT2TGD6BS" target="_blank" class="underline">#dongle</a> :)</li>
            </div>
        
                    </div>
                </div>
            </section>
            <footer class="w-full h-80 mb-6 px-6 mt-2">
                <div class="bg-light-blue w-full h-full px-4 flex flex-col pt-4">
                    <h1 class="text-6xl font-bold font-hk flex items-center text-blue leading-4">
                        <span class="">D</span>
                        <div class="xl:mx-1 grid grid-cols-1 grid-rows-1 place-items-center group">
                            <span class="col-start-1 row-start-1 leading-10">O</span>
                            <img src={star} alt="" class="w-8 lg:w-12 col-start-1 row-start-1 animate-[spin_8s_linear_infinite]" />
                        </div>
                        <span class="">N</span>
                        <span class="">G</span>
                        <span class="">L</span>
                        <span class="">E</span>
                    </h1>
                    <p class="font-semibold text-blue">Made for teens, by teens</p>

                    <ul class="text-blue list-none mt-auto mb-8 underline">
                        <li><a href="https://hackclub.com" class="hover:font-semibold transition-all duration-40">Hack Club</a></li>
                        <li><a href="https://slack.hackclub.com" class="hover:font-semibold transition-all duration-40">Join our Slack</a></li>
                        <li><a href="https://hackclub.com/privacy-and-terms" class="hover:font-semibold transition-all duration-40" target="_blank">Privacy Policy</a></li>
                        <li><a href="https://forms.hackclub.com/bounty" class="hover:font-semibold transition-all duration-40" target="_blank">Fulfillment Bounty</a></li>
                    </ul>
                    <img src={flower} alt="" class="absolute bottom-14 right-14">    
                </div>
            </footer>
            
            <!-- lines -->
            <div class="absolute -z-1 top-0 left-0 h-full w-screen opacity-60 select-none">
                <div class="borders absolute top-0 left-0 h-6 w-screen border-b pl-10 text-sm flex items-end ">//MANUFACTURER: HACK CLUB & SOPHIA
                </div>
                <div class="absolute top-0 left-0 h-full w-6 border-r text-sm">
                    <div class="borders -rotate-90 translate-y-180 whitespace-nowrap">0x1234 Product ID:DONGLE-YSWS</div> 
                </div>
                <div class="absolute top-0 right-0 h-full w-6 border-l">
                </div>
                <div class="absolute bottom-0 left-0 h-6 w-full border-t">
                </div>
            </div>
        </main>
