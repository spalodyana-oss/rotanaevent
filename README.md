<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Tree of Life - Event Reminder</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Chosen Palette: Serene Spa Tones -->
    <!-- Application Structure Plan: The application is designed as a single-page, top-to-bottom narrative flow, ideal for a mobile-first user experience. It starts with a Hero section for immediate access to critical information (what, when, where). This is followed by an interactive timeline for the event schedule, which allows users to engage with the content rather than just read it. Key practical details are then organized into distinct cards for clarity (preparation, what to expect). The structure concludes with location details and a footer. This logical progression guides the user from essential information to detailed planning, making the reminder both elegant and highly functional. -->
    <!-- Visualization & Content Choices: Report Info: Event Schedule -> Goal: Organize & Inform -> Viz/Presentation Method: Interactive Vertical Timeline -> Interaction: On-click highlight of schedule items -> Justification: A visual timeline is more engaging and easier to parse than a static bulleted list. The subtle interaction encourages exploration and focus. | Report Info: Preparation Details (dress code, items to bring) -> Goal: Inform -> Viz/Presentation Method: Thematic Cards -> Interaction: None -> Justification: Grouping distinct pieces of practical advice into visually separate cards enhances readability and makes the information quickly scannable for attendees. | NO charts are necessary as the source material is qualitative and descriptive. -->
    <!-- CONFIRMATION: NO SVG graphics used. NO Mermaid JS used. -->
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;700&family=Poppins:wght@300;400;600&display=swap');
        body {
            font-family: 'Poppins', sans-serif;
            background-color: #F8F5F2; /* Warm Neutral Background */
        }
        h1, h2, h3 {
            font-family: 'Playfair Display', serif;
        }
        .timeline-item.active .timeline-dot {
            transform: scale(1.5);
            background-color: #8D9B6A; /* Accent Green */
        }
        .timeline-item.active .timeline-content {
            border-color: #8D9B6A;
            box-shadow: 0 4px 12px rgba(0,0,0,0.08);
        }
        .timeline-connector {
            width: 2px;
            background-color: #D3C5B5; /* Muted accent */
            position: absolute;
            left: 1.25rem;
            top: 1.25rem;
            bottom: 1.25rem;
            transform: translateX(-50%);
        }
        .btn-primary {
            transition: all 0.3s ease;
        }
        .btn-primary:hover {
            transform: translateY(-2px);
            box-shadow: 0 6px 15px rgba(141, 155, 106, 0.3);
        }
    </style>
</head>
<body class="text-gray-700 antialiased">

    <main class="container mx-auto px-4 py-8 md:py-16 max-w-4xl">

        <!-- Header Section -->
        <header class="text-center mb-12 md:mb-16">
            <h3 class="text-lg text-gray-500 tracking-widest">A Reminder From LODYana Spa</h3>
            <h1 class="text-4xl md:text-6xl font-bold text-[#6a6f4c] mt-2 mb-4">Tree of Life</h1>
            <h2 class="text-2xl md:text-3xl text-gray-600 mb-8">Wellness Awareness Event</h2>
            <p class="max-w-2xl mx-auto text-base">We are excited to welcome you to the upcoming event. Below are the full details for your day of wellness and rejuvenation.</p>
        </header>

        <!-- Key Details Section -->
        <section class="bg-white rounded-2xl shadow-lg p-6 md:p-8 mb-12 md:mb-16">
            <div class="grid grid-cols-1 md:grid-cols-3 gap-6 text-center">
                <div class="flex flex-col items-center">
                    <div class="text-4xl mb-2">🗓️</div>
                    <h3 class="font-semibold text-lg text-gray-800">Date</h3>
                    <p class="text-gray-600">Wednesday, Sept 3rd</p>
                </div>
                <div class="flex flex-col items-center">
                    <div class="text-4xl mb-2">🕙</div>
                    <h3 class="font-semibold text-lg text-gray-800">Time</h3>
                    <p class="text-gray-600">10:00 AM Start</p>
                    <p class="text-sm text-gray-500">(Please arrive at 9:30 AM)</p>
                </div>
                <div class="flex flex-col items-center">
                    <div class="text-4xl mb-2">📍</div>
                    <h3 class="font-semibold text-lg text-gray-800">Location</h3>
                    <p class="text-gray-600">Khalidiya Palace Rayhaan</p>
                </div>
            </div>
        </section>

        <!-- Interactive Schedule Section -->
        <section>
            <h2 class="text-3xl font-bold text-center mb-10 text-[#6a6f4c]">Your Journey for the Day</h2>
             <div class="intro-text text-center max-w-2xl mx-auto mb-12">
                <p>This is the schedule for our morning together. We have curated a series of sessions to help you connect with your inner self and discover new paths to wellness. Click on any item below to highlight it and see the flow of our event.</p>
            </div>
            <div id="timeline-container" class="relative">
                <!-- Timeline Connector Line -->
                <div class="timeline-connector"></div>

                <!-- Timeline Items will be inserted here by JS -->
            </div>
        </section>

        <!-- Preparation & Amenities Section -->
        <section class="mt-16">
            <h2 class="text-3xl font-bold text-center mb-10 text-[#6a6f4c]">How to Prepare</h2>
            <div class="intro-text text-center max-w-2xl mx-auto mb-12">
                <p>To ensure you have the most comfortable and enriching experience, here are a few suggestions for the day. This section covers what to wear, what to bring, and what delightful refreshments will be available.</p>
            </div>
            <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
                <div class="bg-white p-6 rounded-2xl shadow-lg">
                    <h3 class="font-bold text-xl mb-3 text-gray-800">Comfortable Attire</h3>
                    <p>For the meditation session, we kindly ask you to wear comfortable cotton clothes. This will allow for ease of movement and breathability as we move through the session.</p>
                </div>
                <div class="bg-white p-6 rounded-2xl shadow-lg">
                    <h3 class="font-bold text-xl mb-3 text-gray-800">Mat Requirement</h3>
                    <p>For the meditation session, it is mandatory to bring your own mat. This ensures your comfort and a personalized experience.</p>
                </div>
                 <div class="bg-white p-6 rounded-2xl shadow-lg">
                    <h3 class="font-bold text-xl mb-3 text-gray-800">Our Specialists</h3>
                    <p>Meet our esteemed guide, Sensei Jo, who will lead the meditation journey. You'll also have the opportunity to connect with the LODYana Spa specialist team during the afternoon session.</p>
                </div>
                <div class="bg-white p-6 rounded-2xl shadow-lg">
                    <h3 class="font-bold text-xl mb-3 text-gray-800">Healthy Refreshments</h3>
                    <p>Throughout the event, we will be serving a selection of healthy snacks and detox drinks to nourish your body as we nourish your soul. Enjoy them at your leisure.</p>
                </div>
            </div>
        </section>
        
        <!-- Location Link Section -->
        <section class="text-center mt-16 bg-white p-8 rounded-2xl shadow-lg">
             <h2 class="text-3xl font-bold text-center mb-4 text-[#6a6f4c]">Find Your Way to Us</h2>
             <p class="max-w-xl mx-auto mb-6">The event is located at the beautiful Khalidiya Palace Rayhaan by Rotana. For easy directions, please use the link below.</p>
             <a href="https://maps.app.goo.gl/Z7xixiJ7c8oNyekXA" target="_blank" rel="noopener noreferrer" class="inline-block bg-[#8D9B6A] text-white font-bold py-3 px-8 rounded-full text-lg btn-primary">
                Open in Google Maps
             </a>
        </section>


    </main>
    
    <!-- Footer -->
    <footer class="text-center py-8">
        <p class="text-gray-500">We look forward to sharing this beautiful experience with you.</p>
        <p class="font-bold text-lg text-gray-600 mt-2">The LODYana Spa Team ✨</p>
    </footer>

    <script>
        document.addEventListener('DOMContentLoaded', function() {
            const scheduleData = [
                { time: '9:30 AM', title: 'Guest Arrival & Welcome', description: 'Arrive, settle in, and enjoy a warm welcome from our team.' },
                { time: '10:00 AM', title: 'Introduction & Welcome', description: 'Official start of the event with an introduction to the day\'s journey.' },
                { time: '10:15 AM', title: 'Introduction to Sensei Jo', description: 'Meet our guide for the day, Sensei Jo, and learn about their philosophy.' },
                { time: '10:30 AM', title: 'The Meaning of Meditation', description: 'A talk on how to blend inner and outer beauty through mindfulness.' },
                { time: '11:00 AM', title: '"Travel with Sensei Jo"', description: 'An immersive Ancient Breathing Meditation Session to center your mind and body.' },
                { time: '12:00 PM', title: 'Soul Space & Hot Herbal Drinks', description: 'A moment to pause, reflect, and enjoy soothing herbal beverages.' },
                { time: '12:10 PM', title: 'Meet Our Specialist Team', description: 'Connect with our experts, learn about treatments, and receive giveaways and gifts.' }
            ];

            const timelineContainer = document.getElementById('timeline-container');
            
            scheduleData.forEach((item, index) => {
                const timelineItem = document.createElement('div');
                timelineItem.className = 'timeline-item relative flex items-start mb-8 cursor-pointer';
                if (index === 0) timelineItem.classList.add('active');

                timelineItem.innerHTML = `
                    <div class="flex-shrink-0 w-10 h-10 bg-white border-2 border-[#D3C5B5] rounded-full flex items-center justify-center transition-all duration-300 timeline-dot">
                        <div class="w-3 h-3 bg-[#D3C5B5] rounded-full"></div>
                    </div>
                    <div class="ml-6 flex-grow bg-white p-5 rounded-xl border-2 border-transparent transition-all duration-300 timeline-content">
                        <p class="font-bold text-gray-500 text-sm">${item.time}</p>
                        <h4 class="font-bold text-lg text-gray-800 mt-1">${item.title}</h4>
                        <p class="text-gray-600 mt-2 text-sm">${item.description}</p>
                    </div>
                `;
                timelineContainer.appendChild(timelineItem);
            });

            const timelineItems = document.querySelectorAll('.timeline-item');
            timelineItems.forEach(item => {
                item.addEventListener('click', () => {
                    timelineItems.forEach(i => i.classList.remove('active'));
                    item.classList.add('active');
                });
            });
        });
    </script>

</body>
</html>
