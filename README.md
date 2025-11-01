# calculater
إقامة عمليات حسابية
<!DOCTYPE html> 
3	<html lang="ar"> 
4	<head> 
5	    <meta charset="UTF-8"> 
6	    <meta name="viewport" content="width=device-width, initial-scale=1.0"> 
7	    <title>آلة حاسبة</title> 
8	    <link rel="stylesheet" href="styles.css"> 
9			<style> 
10			.calculator { 
11	    width: 300px; 
12	    margin: 50px auto; 
13	    padding: 20px; 
14	    border: 1px solid #ccc; 
15	    border-radius: 10px; 
16	    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1); 
17	    background-color: #f0f0f0; 
18	} 
19	 
20	#display { 
21	    width: 100%; 
22	    height: 40px; 
23	    font-size: 24px; 
24	    text-align: right; 
25	    padding: 10px; 
26	    border: none; 
27	    border-radius: 10px; 
28	    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1); 
29	    background-color: #fff; 
30	} 
31	 
32	.buttons { 
33	    display: grid; 
34	    grid-template-columns: repeat(4, 1fr); 
35	    gap: 10px; 
36	    margin-top: 20px; 
37	} 
38	 
39	button { 
40	    padding: 10px; 
41	    font-size: 18px; 
42	    border: none; 
43	    border-radius: 10px; 
44	    cursor: pointer; 
45	    transition: background-color 0.3s ease; 
46	} 
47	 
48	.number { 
49	    background-color: #fff; 
50	} 
51	 
52	.number:hover { 
53	    background-color: #ddd; 
54	} 
55	 
56	.operator { 
57	    background-color: #ccc; 
58	} 
59	 
60	.operator:hover { 
61	    background-color: #aaa; 
62	} 
63	 
64	.clear { 
65	    background-color: #ff0000; 
66	    color: #fff; 
67	} 
68	 
69	.clear:hover { 
70	    background-color: #cc0000; 
71	} 
72	 
73			</style> 
74	</head> 
75	<body> 
76	    <div class="calculator"> 
77	        <input type="text" id="display" disabled> 
78	        <div class="buttons"> 
79	            <button class="number" onclick="appendNumber('7')">7</button> 
80	            <button class="number" onclick="appendNumber('8')">8</button> 
81	            <button class="number" onclick="appendNumber('9')">9</button> 
82	            <button class="operator" onclick="appendOperator('/')">/</button> 
83	            <button class="number" onclick="appendNumber('4')">4</button> 
84	            <button class="number" onclick="appendNumber('5')">5</button> 
85	            <button class="number" onclick="appendNumber('6')">6</button> 
86	            <button class="operator" onclick="appendOperator('*')">*</button> 
87	            <button class="number" onclick="appendNumber('1')">1</button> 
88	            <button class="number" onclick="appendNumber('2')">2</button> 
89	            <button class="number" onclick="appendNumber('3')">3</button> 
90	            <button class="operator" onclick="appendOperator('-')">-</button> 
91	            <button class="number" onclick="appendNumber('0')">0</button> 
92	            <button class="operator" onclick="appendOperator('.')">.</button> 
93	            <button class="operator" onclick="calculate()">=</button> 
94	            <button class="operator" onclick="appendOperator('+')">+</button> 
95	            <button class="clear" onclick="clearDisplay()">C</button> 
96	        </div> 
97	    </div> 
98	    <script src="script.js"></script> 
99			<script> 
100			let display = document.getElementById('display'); 
101	let currentNumber = ''; 
102	let previousNumber = ''; 
103	let operator = ''; 
104	 
105	function appendNumber(number) { 
106	    currentNumber += number; 
107	    display.value = currentNumber; 
108	} 
109	 
110	function appendOperator(op) { 
111	    if (currentNumber !== '') { 
112	        previousNumber = currentNumber; 
113	        currentNumber = ''; 
114	        operator = op; 
115	    } 
116	} 
117	 
118	function calculate() { 
119	    if (currentNumber !== '' && previousNumber !== '') { 
120	        let result; 
121	        switch (operator) { 
122	            case '+': 
123	                result = parseFloat(previousNumber) + parseFloat(currentNumber); 
124	                break; 
125	            case '-': 
126	                result = parseFloat(previousNumber) - parseFloat(currentNumber); 
127	                break; 
128	            case '*': 
129	                result = parseFloat(previousNumber) * parseFloat(currentNumber); 
130	                break; 
131	            case '/': 
132	                result = parseFloat(previousNumber) / parseFloat(currentNumber); 
133	                break; 
134	            default: 
135	                result = 0; 
136	        } 
137	        display.value = result; 
138	        currentNumber = result.toString(); 
139	        previousNumber = ''; 
140	        operator = ''; 
141	    } 
142	} 
143	 
144	function clearDisplay() { 
145	    display.value = ''; 
146	    currentNumber = ''; 
147	    previousNumber = ''; 
148	    operator = ''; 
149	} 
150	 
151	 
152			</script> 
153	</body> 
154	</html> 
155	 
