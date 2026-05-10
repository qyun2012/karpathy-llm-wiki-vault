<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>IBD Dietary Interventions: Ultra-Processed Food Restriction</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <script src="https://cdn.plot.ly/plotly-2.35.2.min.js"></script>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Roboto:wght@300;400;500;700&display=swap');
        body { font-family: 'Roboto', sans-serif; background-color: #f8fafc; color: #1e293b; }
        .chart-container { position: relative; width: 100%; max-width: 100%; height: 350px; margin-bottom: 2rem; }
        .card { background-color: white; border-radius: 0.75rem; box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1), 0 2px 4px -1px rgba(0, 0, 0, 0.06); padding: 1.5rem; transition: transform 0.2s; }
        .card:hover { transform: translateY(-2px); box-shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.1), 0 4px 6px -2px rgba(0, 0, 0, 0.05); }
        .text-accent { color: #f97316; }
        .bg-accent { background-color: #f97316; }
        .bg-primary { background-color: #2563eb; }
        .text-primary { color: #2563eb; }
        .bg-secondary { background-color: #0ea5e9; }
        .text-secondary { color: #0ea5e9; }
        .nova-1 { border-left: 4px solid #22c55e; }
        .nova-4 { border-left: 4px solid #ef4444; }
    </style>
</head>
<body class="antialiased">

<header class="bg-primary text-white p-8 md:p-12 shadow-md relative overflow-hidden">
    <div class="absolute top-0 left-0 w-full h-full opacity-10 bg-[radial-gradient(ellipse_at_top_right,_var(--tw-gradient-stops))] from-white via-transparent to-transparent"></div>
    <div class="max-w-6xl mx-auto relative z-10">
        <h1 class="text-4xl md:text-5xl font-bold mb-4 tracking-tight">The PK-Diet Link</h1>
        <p class="text-xl md:text-2xl font-light text-blue-100 max-w-3xl">Targeting Inflammatory Bowel Disease through Ultra-Processed Food Restriction: A Precision Nutrition Approach.</p>
        <div class="mt-8 inline-block bg-white text-primary font-semibold py-2 px-4 rounded-full text-sm shadow">
            Based on recent findings from UoB & NIH Studies
        </div>
    </div>
</header>

<nav class="sticky top-0 bg-white shadow-sm z-50 border-b border-gray-200">
    <div class="max-w-6xl mx-auto px-6 py-4 flex space-x-6 overflow-x-auto text-sm font-medium text-gray-600">
        <a href="#context" class="hover:text-primary whitespace-nowrap transition-colors">The Problem</a>
        <a href="#mechanisms" class="hover:text-primary whitespace-nowrap transition-colors">Mechanisms</a>
        <a href="#nova" class="hover:text-primary whitespace-nowrap transition-colors">NOVA Classification</a>
        <a href="#pk-link" class="hover:text-primary whitespace-nowrap transition-colors">The PK-Diet Link</a>
        <a href="#gba-cded" class="hover:text-primary whitespace-nowrap transition-colors">GBA-CDED Plan</a>
    </div>
</nav>

<main class="max-w-6xl mx-auto px-6 py-12 space-y-16">

    <section id="context" class="scroll-mt-24">
        <div class="mb-8 border-l-4 border-accent pl-4">
            <h2 class="text-3xl font-bold text-gray-800">The Rise of Western Diets and IBD</h2>
            <p class="text-gray-600 mt-2 text-lg">Industrialized environments correlate strongly with surging IBD incidence.</p>
        </div>
        
        <div class="grid grid-cols-1 md:grid-cols-2 gap-8 items-center">
            <div class="space-y-4">
                <p class="text-gray-700 leading-relaxed">
                    The global incidence of Inflammatory Bowel Disease (IBD) is skyrocketing, particularly in newly industrialized regions like China. While genetics play a role, the rapid shift is primarily attributed to environmental factors, notably the adoption of the <strong>Western Diet</strong>.
                </p>
                <p class="text-gray-700 leading-relaxed">
                    This dietary pattern is characterized by high intakes of animal fats, refined sugars, and critically, <strong>Ultra-Processed Foods (UPFs)</strong>. These industrial formulations introduce chemical additives—like emulsifiers and artificial sweeteners—that are increasingly implicated in driving chronic gut inflammation.
                </p>
                <div class="bg-orange-50 p-4 rounded-lg border border-orange-100 flex items-start mt-6">
                    <span class="text-3xl mr-4">&#9888;&#65039;</span>
                    <div>
                        <h4 class="font-bold text-orange-800">Key Risk Factor</h4>
                        <p class="text-sm text-orange-700 mt-1">The PURE study (over 110,000 participants across 21 countries) demonstrated that higher intake of UPFs is significantly associated with an increased risk of developing IBD.</p>
                    </div>
                </div>
            </div>
            <div class="card bg-white">
                <h3 class="text-lg font-bold mb-2 text-center text-gray-700">IBD Incidence Trend vs UPF Consumption</h3>
                <p class="text-xs text-gray-500 text-center mb-4">Conceptual representation showing strong correlation.</p>
                <div class="chart-container h-64">
                    <canvas id="incidenceChart"></canvas>
                </div>
            </div>
        </div>
    </section>

    <section id="mechanisms" class="scroll-mt-24 bg-gray-50 -mx-6 px-6 py-12 border-y border-gray-200">
        <div class="max-w-6xl mx-auto">
            <div class="mb-10 text-center">
                <h2 class="text-3xl font-bold text-gray-800">The "Triple Hit" Mechanism of UPFs</h2>
                <p class="text-gray-600 mt-2 max-w-2xl mx-auto">How ultra-processed ingredients compromise intestinal integrity and drive inflammation.</p>
            </div>

            <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
                <div class="card text-center hover:border-primary border border-transparent">
                    <div class="w-16 h-16 rounded-full bg-blue-100 text-primary flex items-center justify-center text-2xl font-bold mx-auto mb-4 border-2 border-primary">&#129524;</div>
                    <h3 class="font-bold text-lg mb-2 text-gray-800">1. Physical Barrier Disruption</h3>
                    <p class="text-sm text-gray-600">Emulsifiers (like CMC and P-80) act like detergents. They dissolve the protective intestinal mucus layer, allowing bacteria to directly contact and penetrate the gut epithelium.</p>
                </div>
                <div class="card text-center hover:border-secondary border border-transparent">
                    <div class="w-16 h-16 rounded-full bg-sky-100 text-secondary flex items-center justify-center text-2xl font-bold mx-auto mb-4 border-2 border-secondary">&#129440;</div>
                    <h3 class="font-bold text-lg mb-2 text-gray-800">2. Dysbiosis Induction</h3>
                    <p class="text-sm text-gray-600">Artificial sweeteners and specific food additives promote the overgrowth of pro-inflammatory bacteria while reducing microbial diversity, favoring pathogens like Adherent-Invasive E. coli (AIEC).</p>
                </div>
                <div class="card text-center hover:border-accent border border-transparent">
                    <div class="w-16 h-16 rounded-full bg-orange-100 text-accent flex items-center justify-center text-2xl font-bold mx-auto mb-4 border-2 border-accent">&#128293;</div>
                    <h3 class="font-bold text-lg mb-2 text-gray-800">3. Inflammatory Signaling</h3>
                    <p class="text-sm text-gray-600">Processed fats, particularly those high in Omega-6 and trans fats, activate the TLR4/NLRP3 inflammasome axis, triggering a systemic chronic inflammatory response.</p>
                </div>
            </div>

            <div class="mt-12 card bg-white">
                <h3 class="text-xl font-bold mb-4 text-gray-800 border-b pb-2">Evidence Snapshot: The ENIGMA Study</h3>
                <div class="flex flex-col md:flex-row gap-6 items-center">
                    <div class="flex-1">
                        <p class="text-gray-700 text-sm leading-relaxed">
                            Published in <em>GUT</em> (2024), the ENIGMA study (a collaboration between CUHK and UoB) provided crucial evidence linking specific additives to disease activity. It was the first large-scale study to quantify food additive intake and relate it directly to Crohn's Disease.
                        </p>
                        <ul class="mt-4 space-y-2 text-sm text-gray-700">
                            <li class="flex items-start"><span class="text-primary mr-2">&#10003;</span> Quantified emulsifier and sweetener intake.</li>
                            <li class="flex items-start"><span class="text-primary mr-2">&#10003;</span> Established positive correlation with CD activity.</li>
                            <li class="flex items-start"><span class="text-primary mr-2">&#10003;</span> Validated the rationale for restricting UPFs to induce remission.</li>
                        </ul>
                    </div>
                    <div class="flex-1 w-full">
                         <div class="chart-container h-48">
                            <canvas id="enigmaChart"></canvas>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <section id="nova" class="scroll-mt-24">
        <div class="mb-8 border-l-4 border-primary pl-4">
            <h2 class="text-3xl font-bold text-gray-800">Defining the Target: NOVA Classification</h2>
            <p class="text-gray-600 mt-2 text-lg">A systematic approach to categorizing foods based on processing level, not just nutrients.</p>
        </div>

        <p class="text-gray-700 mb-6">
            To implement a UPF-restricted diet, we rely on the NOVA classification system. It shifts the focus from macro-nutrients (fat, carbs, protein) to the <em>extent and purpose</em> of industrial processing. The clinical target is the strict elimination of <strong>Group 4</strong> foods.
        </p>

        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-4">
            <div class="card nova-1 bg-green-50/50">
                <h3 class="font-bold text-green-700 mb-1">NOVA 1</h3>
                <p class="text-xs font-semibold uppercase tracking-wider text-green-600 mb-2">Unprocessed / Minimally Processed</p>
                <p class="text-sm text-gray-600 mb-4 h-16 overflow-hidden">Edible parts of plants or animals, altered only to preserve or make edible without adding substances.</p>
                <div class="text-2xl">&#127815; &#12936A; &#129385;</div>
                <p class="text-xs text-gray-500 mt-2 italic">Fruit, veg, eggs, raw meat.</p>
            </div>
            
            <div class="card border-l-4 border-yellow-400 bg-yellow-50/50">
                <h3 class="font-bold text-yellow-700 mb-1">NOVA 2</h3>
                <p class="text-xs font-semibold uppercase tracking-wider text-yellow-600 mb-2">Processed Culinary Ingredients</p>
                <p class="text-sm text-gray-600 mb-4 h-16 overflow-hidden">Substances extracted from Group 1 or from nature, used to season or cook Group 1 foods.</p>
                <div class="text-2xl">&#129650; &#129472; &#129426;</div>
                <p class="text-xs text-gray-500 mt-2 italic">Oils, butter, sugar, salt.</p>
            </div>

            <div class="card border-l-4 border-orange-400 bg-orange-50/50">
                <h3 class="font-bold text-orange-700 mb-1">NOVA 3</h3>
                <p class="text-xs font-semibold uppercase tracking-wider text-orange-600 mb-2">Processed Foods</p>
                <p class="text-sm text-gray-600 mb-4 h-16 overflow-hidden">Products made by adding Group 2 ingredients to Group 1 foods, usually to increase durability.</p>
                <div class="text-2xl">&#129371; &#127838; &#129472;</div>
                <p class="text-xs text-gray-500 mt-2 italic">Canned veg, fresh bread, cheese.</p>
            </div>

            <div class="card nova-4 bg-red-50/50">
                <h3 class="font-bold text-red-700 mb-1">NOVA 4</h3>
                <p class="text-xs font-semibold uppercase tracking-wider text-red-600 mb-2 flex items-center justify-between">Ultra-Processed Foods <span class="bg-red-500 text-white px-2 py-0.5 rounded text-[10px] font-bold">TARGET</span></p>
                <p class="text-sm text-gray-600 mb-4 h-16 overflow-hidden">Industrial formulations made mostly from substances extracted from foods, often with additives.</p>
                <div class="text-2xl">&#127828; &#129380; &#127849;</div>
                <p class="text-xs text-gray-500 mt-2 italic">Snacks, sodas, instant meals.</p>
            </div>
        </div>

        <div class="mt-8 bg-white p-6 rounded-lg shadow-sm border border-gray-200">
            <h4 class="font-bold text-gray-800 mb-4">Composition of the Target Diet (Conceptual)</h4>
            <div class="chart-container h-64 mx-auto max-w-md">
                 <canvas id="dietCompositionChart"></canvas>
            </div>
             <p class="text-sm text-center text-gray-500 mt-2">The goal is to shift calorie intake entirely away from NOVA 4 towards NOVA 1 & 3.</p>
        </div>
    </section>

    <section id="pk-link" class="scroll-mt-24">
        <div class="mb-8 border-l-4 border-secondary pl-4">
            <h2 class="text-3xl font-bold text-gray-800">The Unique Selling Point: The PK-Diet Link</h2>
            <p class="text-gray-600 mt-2 text-lg">Linking dietary exclusion to biologic drug pharmacokinetics via lipidomic biomarkers.</p>
        </div>

        <p class="text-gray-700 leading-relaxed mb-8">
            This study proposes a novel mechanism: Dietary intervention acts as a <strong>sensitizer for biologic therapies (like Infliximab - IFX)</strong>. We hypothesize that removing UPFs repairs the mucosal barrier, reduces local inflammatory consumption of the drug, and ultimately stabilizes systemic drug clearance.
        </p>

        <div class="grid grid-cols-1 lg:grid-cols-5 gap-4 items-stretch mb-12">
            
            <div class="lg:col-span-1 bg-red-50 rounded-lg p-4 flex flex-col justify-center items-center text-center border border-red-100">
                <span class="text-2xl mb-2">&#127828;</span>
                <span class="font-bold text-sm text-red-800">High UPF Intake</span>
            </div>
            
            <div class="lg:col-span-1 flex items-center justify-center">
                 <span class="text-2xl text-gray-400 hidden lg:block">&#10142;</span>
                 <span class="text-2xl text-gray-400 lg:hidden py-2">&#11015;</span>
            </div>
            
            <div class="lg:col-span-1 bg-yellow-50 rounded-lg p-4 flex flex-col justify-center items-center text-center border border-yellow-100">
                <span class="text-2xl mb-2">&#129524;</span>
                <span class="font-bold text-sm text-yellow-800">Mucosal Barrier Damage (LPS Translocation)</span>
            </div>

            <div class="lg:col-span-1 flex items-center justify-center">
                <span class="text-2xl text-gray-400 hidden lg:block">&#10142;</span>
                <span class="text-2xl text-gray-400 lg:hidden py-2">&#11015;</span>
            </div>

            <div class="lg:col-span-1 bg-blue-50 rounded-lg p-4 flex flex-col justify-center items-center text-center border border-blue-100">
                <span class="text-2xl mb-2">&#128200;</span>
                <span class="font-bold text-sm text-blue-800">High IFX Clearance (CL), Low Trough Levels</span>
            </div>
        </div>

        <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
            <div class="card bg-white">
                <h3 class="text-lg font-bold mb-4 text-gray-800">Biomarker Validation: Lipidomics</h3>
                <p class="text-sm text-gray-600 mb-4">
                    Self-reported dietary questionnaires are notoriously unreliable. We propose using <strong>plasma lipidomics</strong> (specifically assessing n-6:n-3 PUFA ratios and specific ceramides like LacCer) as an objective biomarker for dietary adherence and metabolic state.
                </p>
                <div class="bg-gray-50 p-4 rounded text-sm border-l-2 border-secondary">
                    <p class="font-semibold text-gray-700">The N-6:N-3 Ratio Goal</p>
                    <p class="text-gray-600 mt-1">Aiming for a ratio of <strong>&lt; 3:1</strong> (compared to the typical Western diet >15:1) acts as a primary metric for successful UPF exclusion and anti-inflammatory shift.</p>
                </div>
            </div>
            
            <div class="card bg-white">
                <h3 class="text-lg font-bold mb-4 text-gray-800">Mediation Model Strategy</h3>
                <p class="text-xs text-gray-500 mb-2">Analyzing the causal pathway based on pilot data (746 cases).</p>
                <div class="chart-container h-48">
                    <canvas id="mediationChart"></canvas>
                </div>
                <p class="text-xs text-gray-500 mt-2 text-center">Dietary improvement (measured via lipids) mediates lower clearance through increased Albumin and reduced systemic inflammation.</p>
            </div>
        </div>
    </section>

    <section id="gba-cded" class="scroll-mt-24">
        <div class="mb-8 border-l-4 border-accent pl-4">
            <h2 class="text-3xl font-bold text-gray-800">The GBA-CDED Plan</h2>
            <p class="text-gray-600 mt-2 text-lg">Greater Bay Area Crohn's Disease Exclusion Diet: Culturally Tailored Intervention.</p>
        </div>

        <div class="bg-white p-6 md:p-8 rounded-xl shadow-md border border-gray-100">
            <p class="text-gray-700 leading-relaxed mb-6">
                Directly porting Western diets (like standard CDED requiring potatoes and chicken breast) leads to poor compliance. Drawing inspiration from NIH projects (Damas et al.) that utilize "Tailored American Diets," we propose the <strong>GBA-CDED</strong>. This approach maintains strict NOVA 4 exclusion and targeted nutrient ratios but utilizes local, culturally acceptable staples.
            </p>

            <h3 class="text-xl font-bold mb-4 text-gray-800 border-b pb-2">Localized Ingredient Substitution</h3>
            <div class="overflow-x-auto">
                <table class="w-full text-left border-collapse">
                    <thead>
                        <tr class="bg-gray-50 text-gray-600 text-sm">
                            <th class="p-3 border-b font-semibold">Category</th>
                            <th class="p-3 border-b font-semibold text-red-600">Strictly Excluded (NOVA 4)</th>
                            <th class="p-3 border-b font-semibold text-green-600">GBA Recommended Alternatives (NOVA 1/2)</th>
                        </tr>
                    </thead>
                    <tbody class="text-sm">
                        <tr class="hover:bg-gray-50 transition-colors">
                            <td class="p-3 border-b font-medium text-gray-700">Breakfast</td>
                            <td class="p-3 border-b text-gray-600">Industrial bread, instant oats, canned meats</td>
                            <td class="p-3 border-b text-gray-800">Fresh meat congee (生滚肉粥), steamed sweet potato, boiled eggs</td>
                        </tr>
                        <tr class="hover:bg-gray-50 transition-colors">
                            <td class="p-3 border-b font-medium text-gray-700">Protein</td>
                            <td class="p-3 border-b text-gray-600">Sausages, fried fish fillets, processed meatballs</td>
                            <td class="p-3 border-b text-gray-800">Steamed fish (清蒸鱼), poached chicken without skin (白切鸡)</td>
                        </tr>
                        <tr class="hover:bg-gray-50 transition-colors">
                            <td class="p-3 border-b font-medium text-gray-700">Carbs/Fiber</td>
                            <td class="p-3 border-b text-gray-600">Instant noodles, packaged biscuits, commercial rice noodles</td>
                            <td class="p-3 border-b text-gray-800">Steamed yam/huishan (淮山), lotus root (莲藕), handmade noodles</td>
                        </tr>
                        <tr class="hover:bg-gray-50 transition-colors">
                            <td class="p-3 border-b font-medium text-gray-700">Beverages</td>
                            <td class="p-3 border-b text-gray-600">Commercial milk tea, sodas, concentrated juices</td>
                            <td class="p-3 border-b text-gray-800">Water, approved PEN formulas, clear broths</td>
                        </tr>
                    </tbody>
                </table>
            </div>

            <div class="mt-8 grid grid-cols-1 md:grid-cols-2 gap-6 bg-blue-50 p-6 rounded-lg border border-blue-100">
                <div>
                    <h4 class="font-bold text-blue-900 mb-2">Study Design Strategy</h4>
                    <ul class="list-disc pl-5 space-y-1 text-sm text-blue-800">
                        <li><strong>Design:</strong> Crossover RCT for early mild-to-moderate cases to minimize individual variance.</li>
                        <li><strong>Compliance:</strong> Use 'Grocery Stipends' (e.g., green supermarket cards) or pre-packaged fresh ingredient kits instead of full catered meals.</li>
                        <li><strong>Primary Endpoint:</strong> Change in IFX clearance rate (CL) and mucosal healing at week 14.</li>
                    </ul>
                </div>
                 <div>
                    <h4 class="font-bold text-blue-900 mb-2">Targeted N-6:N-3 Shift</h4>
                    <div id="plotly-fatty-acids" class="w-full h-40"></div>
                </div>
            </div>
        </div>
    </section>

</main>

<footer class="bg-slate-800 text-slate-300 py-8 border-t border-slate-700 text-center">
    <div class="max-w-6xl mx-auto px-6">
        <p class="text-sm">&copy; 2026 IBD Precision Nutrition Research Project. Data visualizations based on synthesis of current clinical evidence.</p>
    </div>
</footer>

<script>
    const primaryColor = '#2563eb';
    const secondaryColor = '#0ea5e9';
    const accentColor = '#f97316';
    const grayColor = '#94a3b8';
    const redColor = '#ef4444';
    const greenColor = '#22c55e';

    const commonTooltip = {
        callbacks: {
            title: function(tooltipItems) {
                const item = tooltipItems[0];
                let label = item.chart.data.labels[item.dataIndex];
                return Array.isArray(label) ? label.join(' ') : label;
            }
        }
    };

    const ctxIncidence = document.getElementById('incidenceChart').getContext('2d');
    new Chart(ctxIncidence, {
        type: 'line',
        data: {
            labels: ['1990', '2000', '2010', '2020', '2026 (Est)'],
            datasets: [
                {
                    label: 'UPF Consumption Index',
                    data: [20, 35, 55, 80, 95],
                    borderColor: accentColor,
                    backgroundColor: 'transparent',
                    borderWidth: 3,
                    yAxisID: 'y',
                    tension: 0.4
                },
                {
                    label: 'IBD Incidence Rate',
                    data: [5, 12, 28, 60, 85],
                    borderColor: primaryColor,
                    backgroundColor: 'rgba(37, 99, 235, 0.1)',
                    borderWidth: 3,
                    fill: true,
                    yAxisID: 'y1',
                    tension: 0.4
                }
            ]
        },
        options: {
            responsive: true,
            maintainAspectRatio: false,
            interaction: { mode: 'index', intersect: false },
            plugins: {
                tooltip: commonTooltip,
                legend: { position: 'bottom', labels: { boxWidth: 12, usePointStyle: true } }
            },
            scales: {
                x: { grid: { display: false } },
                y: { type: 'linear', display: true, position: 'left', title: { display: true, text: 'UPF Index' } },
                y1: { type: 'linear', display: true, position: 'right', grid: { drawOnChartArea: false }, title: { display: true, text: 'Incidence' } }
            }
        }
    });

    const ctxEnigma = document.getElementById('enigmaChart').getContext('2d');
    new Chart(ctxEnigma, {
        type: 'bar',
        data: {
            labels: [
                ['Low Additive', 'Intake'],
                ['Moderate', 'Additive Intake'],
                ['High Additive', 'Intake']
            ],
            datasets: [{
                label: 'Relative Risk of Active Disease',
                data: [1.0, 1.4, 2.1],
                backgroundColor: [grayColor, secondaryColor, redColor],
                borderRadius: 4
            }]
        },
        options: {
            responsive: true,
            maintainAspectRatio: false,
            plugins: {
                tooltip: commonTooltip,
                legend: { display: false }
            },
            scales: {
                y: { beginAtZero: true, title: { display: true, text: 'Relative Risk' } },
                x: { grid: { display: false } }
            }
        }
    });

    const ctxDiet = document.getElementById('dietCompositionChart').getContext('2d');
    new Chart(ctxDiet, {
        type: 'doughnut',
        data: {
            labels: ['NOVA 1 (Unprocessed)', 'NOVA 2 (Ingredients)', 'NOVA 3 (Processed)', 'NOVA 4 (Ultra-Processed)'],
            datasets: [{
                data: [60, 10, 30, 0],
                backgroundColor: [greenColor, '#facc15', '#fb923c', '#fee2e2'],
                borderWidth: 2,
                borderColor: '#fff'
            }]
        },
        options: {
            responsive: true,
            maintainAspectRatio: false,
            cutout: '70%',
            plugins: {
                tooltip: commonTooltip,
                legend: { position: 'right', labels: { usePointStyle: true, boxWidth: 10 } }
            }
        }
    });

    const ctxMediation = document.getElementById('mediationChart').getContext('2d');
    new Chart(ctxMediation, {
        type: 'bubble',
        data: {
            datasets: [
                {
                    label: 'Dietary Improvement',
                    data: [{ x: 10, y: 50, r: 20 }],
                    backgroundColor: greenColor,
                    borderColor: 'white'
                },
                {
                    label: 'Increased Albumin',
                    data: [{ x: 50, y: 70, r: 15 }],
                    backgroundColor: secondaryColor,
                    borderColor: 'white'
                },
                {
                    label: 'Reduced Inflammation',
                    data: [{ x: 50, y: 30, r: 15 }],
                    backgroundColor: accentColor,
                    borderColor: 'white'
                },
                {
                    label: 'Stable IFX Clearance',
                    data: [{ x: 90, y: 50, r: 25 }],
                    backgroundColor: primaryColor,
                    borderColor: 'white'
                }
            ]
        },
        options: {
            responsive: true,
            maintainAspectRatio: false,
            plugins: {
                tooltip: {
                    callbacks: {
                        label: function(context) { return context.dataset.label; }
                    }
                },
                legend: { display: false }
            },
            scales: {
                x: { display: false, min: 0, max: 100 },
                y: { display: false, min: 0, max: 100 }
            },
            layout: { padding: 10 }
        },
        plugins: [{
            id: 'customLines',
            beforeDraw: chart => {
                const ctx = chart.ctx;
                const xAxis = chart.scales.x;
                const yAxis = chart.scales.y;
                ctx.save();
                ctx.strokeStyle = '#cbd5e1';
                ctx.lineWidth = 2;
                ctx.setLineDash([5, 5]);

                const drawLine = (startX, startY, endX, endY) => {
                    ctx.beginPath();
                    ctx.moveTo(xAxis.getPixelForValue(startX), yAxis.getPixelForValue(startY));
                    ctx.lineTo(xAxis.getPixelForValue(endX), yAxis.getPixelForValue(endY));
                    ctx.stroke();
                };

                drawLine(10, 50, 50, 70); // Diet to Albumin
                drawLine(10, 50, 50, 30); // Diet to Inflammation
                drawLine(50, 70, 90, 50); // Albumin to CL
                drawLine(50, 30, 90, 50); // Inflammation to CL

                ctx.restore();
            }
        }]
    });

    const plotlyData = [{
        type: 'bar',
        x: [15, 2.5],
        y: ['Western Diet', 'Target GBA-CDED'],
        orientation: 'h',
        marker: {
            color: [redColor, greenColor]
        }
    }];
    const plotlyLayout = {
        title: { text: 'N-6:N-3 Ratio', font: { size: 14 } },
        margin: { l: 100, r: 20, t: 40, b: 30 },
        xaxis: { title: 'Ratio Value' },
        paper_bgcolor: 'transparent',
        plot_bgcolor: 'transparent',
        height: 160
    };
    const plotlyConfig = { displayModeBar: false, staticPlot: true };
    Plotly.newPlot('plotly-fatty-acids', plotlyData, plotlyLayout, plotlyConfig);

</script>
</body>
</html>