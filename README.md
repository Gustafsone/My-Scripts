# Intro-to-Git-and-Github
Repository for Testing Git and Github.

<!DOCTYPE html>
<html lang="en" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Interactive Syllabus: MATH 113 Intermediate Algebra</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
    <!-- Chosen Palette: Calm Neutrals -->
    <!-- Application Structure Plan: A single-page dashboard design with a sticky top navigation bar for quick access to key sections (Home, Grading, Schedule, Policies, Resources). This thematic structure is more intuitive for students than a linear document, allowing them to find specific information (like grading weights or due dates) instantly. The flow is designed for task-oriented browsing, such as checking the schedule or understanding an assignment's value, which is more aligned with student needs. -->
    <!-- Visualization & Content Choices: 
        1. Grading Breakdown -> Goal: Compare/Inform -> Viz: Interactive Donut Chart -> Interaction: Clicking a chart segment displays detailed information about that assignment type. -> Justification: Visually communicates the weight of each component more effectively than a list. The interaction connects the quantitative data (weights) with qualitative descriptions, enhancing comprehension. -> Library: Chart.js.
        2. Course Schedule -> Goal: Organize/Plan -> Viz: HTML Table -> Interaction: A dropdown filter allows students to view specific assignment types (e.g., only Tests). -> Justification: Transforms a static schedule into a dynamic planning tool, helping students manage their workload. -> Library/Method: Vanilla JS.
        3. Key Policies -> Goal: Inform -> Viz: Accordion Component -> Interaction: Clicking a policy title expands to show the details. -> Justification: Presents dense information in a clean, manageable way, preventing cognitive overload. Users can focus on one policy at a time. -> Library/Method: Vanilla JS.
        CONFIRMING NO SVG/Mermaid. -->
    <!-- CONFIRMATION: NO SVG graphics used. NO Mermaid JS used. -->
    <style>
        body {
            font-family: 'Inter', sans-serif;
            background-color: #f8f7f4;
            color: #333;
        }
        .chart-container {
            position: relative;
            width: 100%;
            max-width: 400px;
            margin-left: auto;
            margin-right: auto;
            height: 400px;
            max-height: 40vh;
        }
        .nav-link {
            transition: color 0.3s, border-bottom-color 0.3s;
        }
        .nav-link.active {
            color: #3b82f6;
            border-bottom-color: #3b82f6;
        }
        .card {
            background-color: #ffffff;
            border: 1px solid #e5e7eb;
            border-radius: 0.75rem;
            box-shadow: 0 4px 6px -1px rgb(0 0 0 / 0.1), 0 2px 4px -2px rgb(0 0 0 / 0.1);
            transition: transform 0.3s, box-shadow 0.3s;
        }
        .card:hover {
            transform: translateY(-4px);
            box-shadow: 0 10px 15px -3px rgb(0 0 0 / 0.1), 0 4px 6px -4px rgb(0 0 0 / 0.1);
        }
    </style>
</head>
<body class="antialiased">

    <header class="bg-white/80 backdrop-blur-lg sticky top-0 z-50 border-b border-gray-200">
        <nav class="container mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex items-center justify-between h-16">
                <div class="flex-shrink-0">
                    <h1 class="text-xl font-bold text-gray-800">MATH 113 Syllabus</h1>
                </div>
                <div class="hidden md:block">
                    <div class="ml-10 flex items-baseline space-x-4">
                        <a href="#home" class="nav-link text-gray-600 hover:text-blue-600 px-3 py-2 rounded-md text-sm font-medium border-b-2 border-transparent">Home</a>
                        <a href="#grading" class="nav-link text-gray-600 hover:text-blue-600 px-3 py-2 rounded-md text-sm font-medium border-b-2 border-transparent">Grading</a>
                        <a href="#schedule" class="nav-link text-gray-600 hover:text-blue-600 px-3 py-2 rounded-md text-sm font-medium border-b-2 border-transparent">Schedule</a>
                        <a href="#policies" class="nav-link text-gray-600 hover:text-blue-600 px-3 py-2 rounded-md text-sm font-medium border-b-2 border-transparent">Policies</a>
                        <a href="#resources" class="nav-link text-gray-600 hover:text-blue-600 px-3 py-2 rounded-md text-sm font-medium border-b-2 border-transparent">Resources</a>
                    </div>
                </div>
            </div>
        </nav>
    </header>

    <main class="container mx-auto px-4 sm:px-6 lg:px-8 py-8 md:py-12">

        <section id="home" class="mb-16 text-center">
            <h2 class="text-3xl md:text-4xl font-bold tracking-tight text-gray-900 mb-4">Welcome to Intermediate Algebra</h2>
            <p class="max-w-3xl mx-auto text-lg text-gray-600 mb-8">This interactive syllabus is your guide for MATH 113. Here you'll find everything you need to know about the course structure, assignments, grading, and schedule. Use the navigation bar to jump to a specific section.</p>
            <div class="card max-w-2xl mx-auto p-6 text-left">
                <h3 class="text-xl font-semibold mb-4 text-gray-800">Instructor & Course Details</h3>
                <div class="grid grid-cols-1 sm:grid-cols-2 gap-4 text-gray-700">
                    <div><strong>Instructor:</strong> Erik Gustafson</div>
                    <div><strong>Email:</strong> Erik.Gustafson@mobap.edu</div>
                    <div><strong>Course:</strong> MATH 113 WDL* WEB</div>
                    <div><strong>Credits:</strong> 3</div>
                    <div class="sm:col-span-2"><strong>Office Hours:</strong> Available anytime. Drop by ADM 222 or request a virtual meeting via Microsoft Teams.</div>
                    <div class="sm:col-span-2"><strong>Structure:</strong> A 15-week online course. Assignments are due weekly by <strong>11:59 p.m. on Sunday</strong>.</div>
                </div>
            </div>
        </section>

        <section id="grading" class="mb-16">
            <div class="text-center mb-12">
                <h2 class="text-3xl font-bold tracking-tight text-gray-900">Grading Breakdown</h2>
                <p class="mt-4 text-lg text-gray-600">Your final grade is determined by a weighted average of several components. Click on a section of the chart below to learn more about each assignment type.</p>
            </div>
            <div class="flex flex-col lg:flex-row items-center gap-8 lg:gap-12">
                <div class="w-full lg:w-1/2">
                    <div class="chart-container">
                        <canvas id="gradingChart"></canvas>
                    </div>
                </div>
                <div class="w-full lg:w-1/2">
                    <div id="grading-details" class="card p-6 min-h-[250px]">
                        <h3 id="details-title" class="text-2xl font-semibold mb-3 text-gray-800">Select a Category</h3>
                        <p id="details-text" class="text-gray-700">Click or tap on a segment of the donut chart to see a detailed description of the assignment category and its requirements.</p>
                    </div>
                </div>
            </div>
        </section>

        <section id="schedule" class="mb-16">
            <div class="text-center mb-12">
                <h2 class="text-3xl font-bold tracking-tight text-gray-900">Course Schedule</h2>
                <p class="mt-4 text-lg text-gray-600">This is a general outline of our 16-week schedule. Use the filter to quickly find weeks with specific assignment types. For exact due dates, always refer to Canvas.</p>
            </div>
            <div class="card p-6">
                <div class="flex justify-end mb-4">
                    <select id="schedule-filter" class="rounded-md border-gray-300 shadow-sm focus:border-blue-500 focus:ring-blue-500">
                        <option value="all">Show All Assignments</option>
                        <option value="Test">Show Tests Only</option>
                        <option value="DB">Show Discussions Only</option>
                    </select>
                </div>
                <div class="overflow-x-auto">
                    <table class="min-w-full divide-y divide-gray-200">
                        <thead class="bg-gray-50">
                            <tr>
                                <th scope="col" class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">Week</th>
                                <th scope="col" class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">Topics</th>
                                <th scope="col" class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">Assignments</th>
                            </tr>
                        </thead>
                        <tbody id="schedule-body" class="bg-white divide-y divide-gray-200">
                        </tbody>
                    </table>
                </div>
            </div>
        </section>

        <section id="policies" class="mb-16">
            <div class="text-center mb-12">
                <h2 class="text-3xl font-bold tracking-tight text-gray-900">Key Policies</h2>
                <p class="mt-4 text-lg text-gray-600">Please familiarize yourself with these important course and university policies. Click each title to expand and read the details.</p>
            </div>
            <div id="accordion-container" class="space-y-4 max-w-4xl mx-auto">
            </div>
        </section>

        <section id="resources" class="mb-16">
            <div class="text-center mb-12">
                <h2 class="text-3xl font-bold tracking-tight text-gray-900">Required Resources</h2>
                <p class="mt-4 text-lg text-gray-600">You will need the following materials and software for this course.</p>
            </div>
            <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
                <div class="card p-6 text-center">
                    <div class="text-4xl mb-4">📚</div>
                    <h3 class="text-lg font-semibold text-gray-800">ALEKS Platform</h3>
                    <p class="text-gray-600 mt-2">Required for homework. ISBN: 9781259620294.</p>
                </div>
                <div class="card p-6 text-center">
                    <div class="text-4xl mb-4">💻</div>
                    <h3 class="text-lg font-semibold text-gray-800">Respondus LockDown Browser</h3>
                    <p class="text-gray-600 mt-2">Required for all tests and the final exam.</p>
                </div>
                <div class="card p-6 text-center">
                    <div class="text-4xl mb-4">🧮</div>
                    <h3 class="text-lg font-semibold text-gray-800">Scientific Calculator</h3>
                    <p class="text-gray-600 mt-2">A physical calculator or the Desmos online calculator is highly recommended.</p>
                </div>
            </div>
        </section>
    </main>

    <footer class="bg-white border-t border-gray-200">
        <div class="container mx-auto py-6 px-4 sm:px-6 lg:px-8 text-center text-gray-500">
            <p>&copy; 2025 Erik Gustafson | Missouri Baptist University</p>
        </div>
    </footer>

    <script>
        document.addEventListener('DOMContentLoaded', function () {
            
            const syllabusData = {
                grading: [
                    { label: 'Homework', value: 25, color: '#60a5fa', description: 'Homework is completed in the ALEKS platform. Each assignment is worth 10 points. ALEKS is an adaptive system, so the number of questions will vary based on your needs.' },
                    { label: 'Discussion Boards', value: 15, color: '#818cf8', description: 'Discussion boards are worth 20 points each: 10 points for your initial post and 10 points for replies to other students.' },
                    { label: 'Quizzes', value: 15, color: '#a78bfa', description: 'There are fifteen quizzes completed in Canvas, each worth 20 points. You get two attempts for each quiz.' },
                    { label: 'Tests', value: 20, color: '#f472b6', description: 'There are eight chapter tests in Canvas, each worth 100 points. You have only one attempt per test. All tests require the Respondus LockDown Browser.' },
                    { label: 'Final Exam', value: 25, color: '#fb923c', description: 'The final is cumulative, worth 100 points, and must be taken with the Respondus LockDown Browser. It is due by December 15.' }
                ],
                schedule: [
                    { week: 1, topics: 'Sections 1.1-1.3', assignments: 'HW, Quiz 1, DB1' },
                    { week: 2, topics: 'Sections 1.4-1.5', assignments: 'HW, Quiz 2, Test 1' },
                    { week: 3, topics: 'Sections 2.1-2.4', assignments: 'HW, Quiz 3, DB 2' },
                    { week: 4, topics: 'Sections 2.5-2.7', assignments: 'HW, Quiz 4, Test 2' },
                    { week: 5, topics: 'Sections 3.1-3.3', assignments: 'HW, Quiz 5, DB 3' },
                    { week: 6, topics: 'Sections 3.4-3.6', assignments: 'HW, Quiz 6, Test 3' },
                    { week: 7, topics: 'Sections 4.1-4.3, 4.7', assignments: 'HW, Quiz 7, DB 4' },
                    { week: 8, topics: 'Sections 5.1-5.4', assignments: 'HW, Quiz 8, Test 4' },
                    { week: 9, topics: 'Sections 6.1-6.5', assignments: 'HW, Quiz 9' },
                    { week: 10, topics: 'Sections 7.1-7.3', assignments: 'HW, Quiz 10, DB 5' },
                    { week: 11, topics: 'Sections 7.4-7.5', assignments: 'HW, Quiz 11, Test 5' },
                    { week: 12, topics: 'Sections 8.1-8.4', assignments: 'HW, Quiz 12, DB 6' },
                    { week: 13, topics: 'Sections 8.5-8.8', assignments: 'HW, Quiz 13, Test 6' },
                    { week: 14, topics: 'Thanksgiving Break', assignments: 'No Assignments Due' },
                    { week: 15, topics: 'Sections 9.1-9.4', assignments: 'HW, Quiz 14, DB 7' },
                    { week: 16, topics: 'Sections 9.5-9.7', assignments: 'HW, Quiz 15, Test 7' },
                    { week: 'Finals', topics: 'Cumulative', assignments: 'DB 8, CLO Assessment, Final Exam' }
                ],
                policies: [
                    { title: 'Attendance Policy', content: 'For this online course, attendance is measured by completing weekly assignments. Simply logging into Canvas does not count as attendance. If you do not submit assignments during a given week, you will be marked as absent.' },
                    { title: 'Late Work Policy', content: 'Any assignment completed after the due date will have a 10% grade reduction per day. To avoid this, please contact me as soon as you know you might have a problem, and we can work out an extension. Communication is key!' },
                    { title: 'Academic Integrity', content: 'The use of AI tools like ChatGPT for coursework is not allowed without prior instructor approval. All major assignments may be checked for originality using Turnitin. Academic honesty is expected in all aspects of this course.' }
                ]
            };

            const gradingChartCtx = document.getElementById('gradingChart').getContext('2d');
            const gradingChart = new Chart(gradingChartCtx, {
                type: 'doughnut',
                data: {
                    labels: syllabusData.grading.map(item => item.label),
                    datasets: [{
                        data: syllabusData.grading.map(item => item.value),
                        backgroundColor: syllabusData.grading.map(item => item.color),
                        borderColor: '#f8f7f4',
                        borderWidth: 4,
                        hoverBorderWidth: 2,
                        hoverBorderColor: '#fff'
                    }]
                },
                options: {
                    responsive: true,
                    maintainAspectRatio: false,
                    cutout: '60%',
                    plugins: {
                        legend: {
                            position: 'bottom',
                            labels: {
                                padding: 20,
                                font: {
                                    size: 14
                                }
                            }
                        },
                        tooltip: {
                            callbacks: {
                                label: function(context) {
                                    let label = context.label || '';
                                    if (label) {
                                        label += ': ';
                                    }
                                    if (context.parsed !== null) {
                                        label += context.parsed + '%';
                                    }
                                    return label;
                                }
                            }
                        }
                    },
                    onClick: (event, elements) => {
                        if (elements.length > 0) {
                            const index = elements[0].index;
                            const selectedData = syllabusData.grading[index];
                            document.getElementById('details-title').textContent = selectedData.label;
                            document.getElementById('details-text').textContent = selectedData.description;
                        }
                    }
                }
            });

            const scheduleBody = document.getElementById('schedule-body');
            const scheduleFilter = document.getElementById('schedule-filter');

            function populateSchedule(filter = 'all') {
                scheduleBody.innerHTML = '';
                const filteredData = syllabusData.schedule.filter(item => {
                    if (filter === 'all') return true;
                    return item.assignments.includes(filter);
                });

                filteredData.forEach(item => {
                    const row = document.createElement('tr');
                    row.innerHTML = `
                        <td class="px-6 py-4 whitespace-nowrap text-sm font-medium text-gray-900">${item.week}</td>
                        <td class="px-6 py-4 whitespace-nowrap text-sm text-gray-500">${item.topics}</td>
                        <td class="px-6 py-4 whitespace-nowrap text-sm text-gray-500">${item.assignments}</td>
                    `;
                    scheduleBody.appendChild(row);
                });
            }

            scheduleFilter.addEventListener('change', (e) => {
                populateSchedule(e.target.value);
            });
            
            populateSchedule();

            const accordionContainer = document.getElementById('accordion-container');
            syllabusData.policies.forEach((policy, index) => {
                const item = document.createElement('div');
                item.className = 'border border-gray-200 rounded-lg bg-white';
                item.innerHTML = `
                    <h2>
                        <button type="button" class="flex items-center justify-between w-full p-5 font-medium text-left text-gray-700 hover:bg-gray-50 focus:outline-none focus:ring-2 focus:ring-blue-300" data-accordion-target="#accordion-body-${index}" aria-expanded="false" aria-controls="accordion-body-${index}">
                            <span>${policy.title}</span>
                            <svg data-accordion-icon class="w-6 h-6 shrink-0 transition-transform duration-300" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7"></path></svg>
                        </button>
                    </h2>
                    <div id="accordion-body-${index}" class="hidden p-5 border-t border-gray-200">
                        <p class="text-gray-600">${policy.content}</p>
                    </div>
                `;
                accordionContainer.appendChild(item);
            });

            accordionContainer.addEventListener('click', (e) => {
                const button = e.target.closest('button');
                if (!button) return;

                const targetId = button.getAttribute('data-accordion-target');
                const body = document.querySelector(targetId);
                const isExpanded = button.getAttribute('aria-expanded') === 'true';
                
                button.setAttribute('aria-expanded', !isExpanded);
                body.classList.toggle('hidden');
                button.querySelector('svg').classList.toggle('rotate-180');
            });
            
            const sections = document.querySelectorAll('section');
            const navLinks = document.querySelectorAll('.nav-link');

            window.addEventListener('scroll', () => {
                let current = '';
                sections.forEach(section => {
                    const sectionTop = section.offsetTop;
                    if (pageYOffset >= sectionTop - 80) {
                        current = section.getAttribute('id');
                    }
                });

                navLinks.forEach(link => {
                    link.classList.remove('active');
                    if (link.getAttribute('href').includes(current)) {
                        link.classList.add('active');
                    }
                });
            });
        });
    </script>
</body>
</html>
