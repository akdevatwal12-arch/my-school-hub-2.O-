<!DOCTYPE html>
<html>
<head>

<title>My Study Hub</title>

<meta name="viewport" content="width=device-width, initial-scale=1.0">

<style>

*{
    box-sizing:border-box;
    margin:0;
    padding:0;
    font-family:Arial,sans-serif;
}

body{
    background:#f4f6fb;
    color:#222;
    transition:.3s;
}

header{
    background:#4f46e5;
    color:white;
    padding:18px;
    display:flex;
    justify-content:space-between;
    align-items:center;
}

header h1{
    font-size:24px;
}

header button{
    border:0;
    padding:10px 14px;
    border-radius:10px;
    cursor:pointer;
}

nav{
    background:white;
    padding:10px;
    display:flex;
    overflow-x:auto;
    gap:6px;
    box-shadow:0 2px 8px #ccc;
}

nav button{
    border:0;
    background:none;
    padding:12px 15px;
    border-radius:10px;
    white-space:nowrap;
    cursor:pointer;
}

nav button:hover{
    background:#eef2ff;
}

.container{
    max-width:1100px;
    margin:auto;
    padding:20px;
}

.page{
    display:none;
}

.active{
    display:block;
}

.card{
    background:white;
    padding:20px;
    border-radius:18px;
    margin-bottom:20px;
    box-shadow:0 4px 12px #ddd;
}

.card h2{
    color:#4f46e5;
    margin-bottom:12px;
}

.dashboard{
    display:grid;
    grid-template-columns:
    repeat(auto-fit,minmax(200px,1fr));
    gap:18px;
}

.stat{
    font-size:32px;
    font-weight:bold;
    color:#4f46e5;
    margin-top:10px;
}

input,textarea,select{
    width:100%;
    padding:13px;
    margin:7px 0;
    border:1px solid #ccc;
    border-radius:10px;
    font-size:15px;
}

textarea{
    min-height:150px;
    resize:vertical;
}

.primary{
    background:#4f46e5;
    color:white;
    border:0;
    padding:12px 16px;
    border-radius:10px;
    cursor:pointer;
}

.delete{
    background:#ef4444;
    color:white;
    border:0;
    padding:7px 10px;
    border-radius:7px;
    cursor:pointer;
}

.note{
    background:#fffbea;
    padding:18px;
    border-left:5px solid #f59e0b;
    border-radius:10px;
    margin-top:12px;
}

.note p{
    white-space:pre-wrap;
    margin:8px 0;
}

.event{
    background:#eef2ff;
    padding:18px;
    border-left:5px solid #4f46e5;
    border-radius:10px;
    margin-top:12px;
}

.eventDate{
    color:#4f46e5;
    font-weight:bold;
}

.homework{
    background:#f7f7ff;
    padding:18px;
    border-left:5px solid #4f46e5;
    border-radius:10px;
    margin-top:12px;
}

.done{
    opacity:.5;
    text-decoration:line-through;
}

.bookGrid{
    display:grid;
    grid-template-columns:
    repeat(auto-fit,minmax(220px,1fr));
    gap:15px;
}

.book{
    background:#eef2ff;
    padding:20px;
    border-radius:15px;
}

.book h3{
    margin-bottom:8px;
}

.book a{
    display:inline-block;
    margin-top:12px;
    color:#4f46e5;
    font-weight:bold;
    text-decoration:none;
}

.pdf{
    background:#f5f5f5;
    padding:15px;
    border-radius:10px;
    margin-top:10px;
    display:flex;
    justify-content:space-between;
    align-items:center;
    gap:10px;
}

.pdf a{
    color:#4f46e5;
    font-weight:bold;
}

li{
    list-style:none;
    background:#f1f1f1;
    padding:13px;
    margin-top:8px;
    border-radius:9px;
}

li button{
    float:right;
}

.resultBox{
    background:#eef2ff;
    padding:20px;
    border-radius:15px;
    margin-top:15px;
}

.resultNumber{
    font-size:28px;
    font-weight:bold;
    color:#4f46e5;
}

footer{
    text-align:center;
    padding:25px;
    color:#777;
}

.search{
    margin-bottom:20px;
}

/* DARK MODE */

.dark{
    background:#18181b;
    color:white;
}

.dark nav,
.dark .card{
    background:#27272a;
    color:white;
}

.dark input,
.dark textarea,
.dark select{
    background:#27272a;
    color:white;
    border-color:#555;
}

.dark li,
.dark .pdf{
    background:#3f3f46;
}

.dark .note{
    background:#3f3a20;
}

.dark .event,
.dark .book,
.dark .homework,
.dark .resultBox{
    background:#312e81;
}

/* MOBILE */

@media(max-width:600px){

    header{
        flex-direction:column;
        gap:10px;
        text-align:center;
    }

    header h1{
        font-size:21px;
    }

    .container{
        padding:12px;
    }

}

</style>

</head>

<body>


<!-- HEADER -->

<header>

    <h1>📚 My Study Hub</h1>

    <button onclick="toggleDark()">
        🌙 Dark Mode
    </button>

</header>


<!-- NAVIGATION -->

<nav>

    <button onclick="page('home')">
        🏠 Home
    </button>

    <button onclick="page('notes')">
        📝 Notes
    </button>

    <button onclick="page('events')">
        📅 Events
    </button>

    <button onclick="page('homework')">
        📚 Homework
    </button>

    <button onclick="page('pdfs')">
        📂 PDFs
    </button>

    <button onclick="page('ncert')">
        📖 NCERT
    </button>

    <button onclick="page('marks')">
        📊 Marks
    </button>

    <button onclick="page('todo')">
        ✅ To-Do
    </button>

</nav>


<div class="container">


<!-- SEARCH -->

<div class="search">

<input
id="search"
placeholder="🔍 Search your study hub..."
onkeyup="searchAll()">

</div>


<!-- ================= HOME ================= -->

<section id="home" class="page active">

<div class="card">

<h2>Welcome to My Study Hub 👋</h2>

<p>
Everything you need for school in one place.
</p>

</div>


<div class="dashboard">


<div class="card">

<h2>📝 Notes</h2>

<p>Saved notes</p>

<div
class="stat"
id="noteCount">
0
</div>

</div>


<div class="card">

<h2>📅 Events</h2>

<p>Important events</p>

<div
class="stat"
id="eventCount">
0
</div>

</div>


<div class="card">

<h2>📂 PDFs</h2>

<p>Your PDF links</p>

<div
class="stat"
id="pdfCount">
0
</div>

</div>


<div class="card">

<h2>✅ Tasks</h2>

<p>Things to do</p>

<div
class="stat"
id="taskCount">
0
</div>

</div>


</div>

</section>


<!-- ================= NOTES ================= -->

<section id="notes" class="page">

<div class="card">

<h2>📝 Write a Note</h2>

<input
id="noteTitle"
placeholder="Note title">

<textarea
id="noteText"
placeholder="Write anything here..."></textarea>

<button
class="primary"
onclick="addNote()">

Save Note

</button>

</div>


<div class="card">

<h2>My Notes</h2>

<div id="notesList"></div>

</div>

</section>


<!-- ================= EVENTS ================= -->

<section id="events" class="page">

<div class="card">

<h2>📅 Add Event</h2>

<input
id="eventName"
placeholder="Event name">

<input
id="eventDate"
type="date">

<input
id="eventInfo"
placeholder="Description">

<button
class="primary"
onclick="addEvent()">

Add Event

</button>

</div>


<div class="card">

<h2>Upcoming Events</h2>

<div id="eventsList"></div>

</div>

</section>


<!-- ================= HOMEWORK ================= -->

<section id="homework" class="page">

<div class="card">

<h2>📚 Add Homework</h2>

<input
id="hwSubject"
placeholder="Subject">

<textarea
id="hwText"
placeholder="Homework details"></textarea>

<input
id="hwDate"
type="date">

<button
class="primary"
onclick="addHomework()">

Add Homework

</button>

</div>


<div class="card">

<h2>My Homework</h2>

<div id="homeworkList"></div>

</div>

</section>


<!-- ================= PDFS ================= -->

<section id="pdfs" class="page">

<div class="card">

<h2>📂 My PDFs</h2>

<p>
Save links to worksheets, notes and study material.
</p>

<input
id="pdfName"
placeholder="PDF name">

<input
id="pdfLink"
placeholder="Paste PDF link">

<button
class="primary"
onclick="addPDF()">

Add PDF

</button>

</div>


<div class="card">

<h2>Saved PDFs</h2>

<div id="pdfList"></div>

</div>

</section>


<!-- ================= NCERT ================= -->

<section id="ncert" class="page">

<div class="card">

<h2>📖 NCERT Library</h2>

<p>
Choose your class and open the official
NCERT textbook library.
</p>

<br>


<div class="bookGrid">


<div class="book">

<h3>📘 Class 6</h3>

<p>NCERT Textbooks</p>

<a
href="https://ncert.nic.in/textbook.php"
target="_blank">

Open Books →

</a>

</div>


<div class="book">

<h3>📗 Class 7</h3>

<p>NCERT Textbooks</p>

<a
href="https://ncert.nic.in/textbook.php"
target="_blank">

Open Books →

</a>

</div>


<div class="book">

<h3>📙 Class 8</h3>

<p>NCERT Textbooks</p>

<a
href="https://ncert.nic.in/textbook.php"
target="_blank">

Open Books →

</a>

</div>


<div class="book">

<h3>📕 Class 9</h3>

<p>NCERT Textbooks</p>

<a
href="https://ncert.nic.in/textbook.php"
target="_blank">

Open Books →

</a>

</div>


<div class="book">

<h3>📔 Class 10</h3>

<p>NCERT Textbooks</p>

<a
href="https://ncert.nic.in/textbook.php"
target="_blank">

Open Books →

</a>

</div>


<div class="book">

<h3>📚 Class 11</h3>

<p>NCERT Textbooks</p>

<a
href="https://ncert.nic.in/textbook.php"
target="_blank">

Open Books →

</a>

</div>


<div class="book">

<h3>📚 Class 12</h3>

<p>NCERT Textbooks</p>

<a
href="https://ncert.nic.in/textbook.php"
target="_blank">

Open Books →

</a>

</div>


</div>

</div>

</section>


<!-- ================= MARKS CALCULATOR ================= -->

<section id="marks" class="page">

<div class="card">

<h2>📊 Marks Calculator</h2>

<p>
Enter your marks for each subject.
</p>


<input
id="english"
type="number"
min="0"
max="100"
placeholder="English / 100">


<input
id="hindi"
type="number"
min="0"
max="100"
placeholder="Hindi / 100">


<input
id="maths"
type="number"
min="0"
max="100"
placeholder="Mathematics / 100">


<input
id="science"
type="number"
min="0"
max="100"
placeholder="Science / 100">


<input
id="social"
type="number"
min="0"
max="100"
placeholder="Social Science / 100">


<input
id="computer"
type="number"
min="0"
max="100"
placeholder="Computer / 100">


<br>


<button
class="primary"
onclick="calculateMarks()">

Calculate 📊

</button>

</div>


<div
class="card"
id="marksResult"
style="display:none;">

<h2>📋 Your Result</h2>


<div class="resultBox">

<p>Total Marks</p>

<div
class="resultNumber"
id="totalMarks">

0

</div>

</div>


<div class="resultBox">

<p>Percentage</p>

<div
class="resultNumber">

<span id="percentage">
0
</span>%

</div>

</div>


<div class="resultBox">

<p>Average Marks</p>

<div
class="resultNumber"
id="average">

0

</div>

</div>


<div class="resultBox">

<p>Grade</p>

<div
class="resultNumber"
id="grade">

-

</div>

</div>


</div>

</section>


<!-- ================= TODO ================= -->

<section id="todo" class="page">

<div class="card">

<h2>✅ To-Do List</h2>

<input
id="taskInput"
placeholder="Enter a task">

<button
class="primary"
onclick="addTask()">

Add Task

</button>

<ul id="taskList"></ul>

</div>

</section>


</div>


<footer>

My Study Hub © 2026

</footer>


<script>


/* ================= PAGE ================= */

function page(name){

    document
    .querySelectorAll(".page")
    .forEach(function(p){

        p.classList.remove("active");

    });

    document
    .getElementById(name)
    .classList.add("active");

}


/* ================= DARK MODE ================= */

function toggleDark(){

    document.body
    .classList.toggle("dark");

}


/* ================= NOTES ================= */

function addNote(){

    let title =
    document
    .getElementById("noteTitle")
    .value.trim();

    let text =
    document
    .getElementById("noteText")
    .value.trim();


    if(!title || !text){

        alert("Please enter a title and note.");

        return;

    }


    let notes =
    JSON.parse(
        localStorage.getItem("notes")
    ) || [];


    notes.push({

        title:title,
        text:text

    });


    localStorage.setItem(
        "notes",
        JSON.stringify(notes)
    );


    document.getElementById("noteTitle")
    .value="";

    document.getElementById("noteText")
    .value="";


    loadNotes();

}


function loadNotes(){

    let notes =
    JSON.parse(
        localStorage.getItem("notes")
    ) || [];


    let list =
    document.getElementById("notesList");


    list.innerHTML="";


    notes.forEach(function(note,index){

        let div =
        document.createElement("div");


        div.className="note";


        div.innerHTML=`

        <h3>${escapeHTML(note.title)}</h3>

        <p>${escapeHTML(note.text)}</p>

        <button
        class="delete"
        onclick="deleteNote(${index})">

        Delete

        </button>

        `;


        list.appendChild(div);

    });


    document.getElementById("noteCount")
    .innerText=notes.length;

}


function deleteNote(index){

    let notes =
    JSON.parse(
        localStorage.getItem("notes")
    ) || [];


    notes.splice(index,1);


    localStorage.setItem(
        "notes",
        JSON.stringify(notes)
    );


    loadNotes();

}


/* ================= EVENTS ================= */

function addEvent(){

    let name =
    document
    .getElementById("eventName")
    .value.trim();


    let date =
    document
    .getElementById("eventDate")
    .value;


    let info =
    document
    .getElementById("eventInfo")
    .value.trim();


    if(!name || !date){

        alert("Enter the event name and date.");

        return;

    }


    let events =
    JSON.parse(
        localStorage.getItem("events")
    ) || [];


    events.push({

        name:name,
        date:date,
        info:info

    });


    localStorage.setItem(
        "events",
        JSON.stringify(events)
    );


    document.getElementById("eventName")
    .value="";

    document.getElementById("eventDate")
    .value="";

    document.getElementById("eventInfo")
    .value="";


    loadEvents();

}


function loadEvents(){

    let events =
    JSON.parse(
        localStorage.getItem("events")
    ) || [];


    let list =
    document.getElementById("eventsList");


    list.innerHTML="";


    events.forEach(function(event,index){

        let div =
        document.createElement("div");


        div.className="event";


        div.innerHTML=`

        <div class="eventDate">
        📅 ${event.date}
        </div>

        <h3>${escapeHTML(event.name)}</h3>

        <p>${escapeHTML(event.info)}</p>

        <br>

        <button
        class="delete"
        onclick="deleteEvent(${index})">

        Delete

        </button>

        `;


        list.appendChild(div);

    });


    document.getElementById("eventCount")
    .innerText=events.length;

}


function deleteEvent(index){

    let events =
    JSON.parse(
        localStorage.getItem("events")
    ) || [];


    events.splice(index,1);


    localStorage.setItem(
        "events",
        JSON.stringify(events)
    );


    loadEvents();

}


/* ================= HOMEWORK ================= */

function addHomework(){

    let subject =
    document
    .getElementById("hwSubject")
    .value.trim();


    let text =
    document
    .getElementById("hwText")
    .value.trim();


    let date =
    document
    .getElementById("hwDate")
    .value;


    if(!subject || !text || !date){

        alert("Please fill all fields.");

        return;

    }


    let homework =
    JSON.parse(
        localStorage.getItem("homework")
    ) || [];


    homework.push({

        subject:subject,
        text:text,
        date:date,
        done:false

    });


    localStorage.setItem(
        "homework",
        JSON.stringify(homework)
    );


    document.getElementById("hwSubject")
    .value="";

    document.getElementById("hwText")
    .value="";

    document.getElementById("hwDate")
    .value="";


    loadHomework();

}


function loadHomework(){

    let homework =
    JSON.parse(
        localStorage.getItem("homework")
    ) || [];


    let list =
    document.getElementById("homeworkList");


    list.innerHTML="";


    homework.forEach(function(hw,index){

        let div =
        document.createElement("div");


        div.className="homework";


        if(hw.done){

            div.classList.add("done");

        }


        div.innerHTML=`

        <h3>${escapeHTML(hw.subject)}</h3>

        <p>${escapeHTML(hw.text)}</p>

        <small>Due: ${hw.date}</small>

        <br><br>

        <button
        class="primary"
        onclick="toggleHomework(${index})">

        ${hw.done ? "↩️ Undo" : "✅ Complete"}

        </button>

        <button
        class="delete"
        onclick="deleteHomework(${index})">

        Delete

        </button>

        `;


        list.appendChild(div);

    });

}


function toggleHomework(index){

    let homework =
    JSON.parse(
        localStorage.getItem("homework")
    ) || [];


    homework[index].done =
    !homework[index].done;


    localStorage.setItem(
        "homework",
        JSON.stringify(homework)
    );


    loadHomework();

}


function deleteHomework(index){

    let homework =
    JSON.parse(
        localStorage.getItem("homework")
    ) || [];


    homework.splice(index,1);


    localStorage.setItem(
        "homework",
        JSON.stringify(homework)
    );


    loadHomework();

}


/* ================= PDFS ================= */

function addPDF(){

    let name =
    document
    .getElementById("pdfName")
    .value.trim();


    let link =
    document
    .getElementById("pdfLink")
    .value.trim();


    if(!name || !link){

        alert("Enter the PDF name and link.");

        return;

    }


    let pdfs =
    JSON.parse(
        localStorage.getItem("pdfs")
    ) || [];


    pdfs.push({

        name:name,
        link:link

    });


    localStorage.setItem(
        "pdfs",
        JSON.stringify(pdfs)
    );


    document.getElementById("pdfName")
    .value="";

    document.getElementById("pdfLink")
    .value="";


    loadPDFs();

}


function loadPDFs(){

    let pdfs =
    JSON.parse(
        localStorage.getItem("pdfs")
    ) || [];


    let list =
    document.getElementById("pdfList");


    list.innerHTML="";


    pdfs.forEach(function(pdf,index){

        let div =
        document.createElement("div");


        div.className="pdf";


        div.innerHTML=`

        <span>
        📄 ${escapeHTML(pdf.name)}
        </span>

        <span>

        <a
        href="${escapeAttribute(pdf.link)}"
        target="_blank">

        Open

        </a>

        &nbsp;

        <button
        class="delete"
        onclick="deletePDF(${index})">

        Delete

        </button>

        </span>

        `;


        list.appendChild(div);

    });


    document.getElementById("pdfCount")
    .innerText=pdfs.length;

}


function deletePDF(index){

    let pdfs =
    JSON.parse(
        localStorage.getItem("pdfs")
    ) || [];


    pdfs.splice(index,1);


    localStorage.setItem(
        "pdfs",
        JSON.stringify(pdfs)
    );


    loadPDFs();

}


/* ================= MARKS CALCULATOR ================= */

function calculateMarks(){

    let subjects = [

        "english",
        "hindi",
        "maths",
        "science",
        "social",
        "computer"

    ];


    let total = 0;


    for(let i=0;i<subjects.length;i++){

        let input =
        document
        .getElementById(subjects[i]);


        let mark = Number(input.value);


        if(
            input.value === "" ||
            mark < 0 ||
            mark > 100
        ){

            alert(
                "Please enter marks between 0 and 100 for every subject."
            );

            return;

        }


        total += mark;

    }


    let percentage =
    (total / 600) * 100;


    let average =
    total / 6;


    let grade;


    if(percentage >= 90){

        grade="A+";

    }

    else if(percentage >= 80){

        grade="A";

    }

    else if(percentage >= 70){

        grade="B";

    }

    else if(percentage >= 60){

        grade="C";

    }

    else if(percentage >= 50){

        grade="D";

    }

    else{

        grade="Needs Improvement";

    }


    document.getElementById("totalMarks")
    .innerText=total + " / 600";


    document.getElementById("percentage")
    .innerText=percentage.toFixed(2);


    document.getElementById("average")
    .innerText=average.toFixed(2);


    document.getElementById("grade")
    .innerText=grade;


    document.getElementById("marksResult")
    .style.display="block";

}


/* ================= TODO ================= */

function addTask(){

    let input =
    document.getElementById("taskInput");


    let task =
    input.value.trim();


    if(!task){

        alert("Enter a task.");

        return;

    }


    let tasks =
    JSON.parse(
        localStorage.getItem("tasks")
    ) || [];


    tasks.push(task);


    localStorage.setItem(
        "tasks",
        JSON.stringify(tasks)
    );


    input.value="";


    loadTasks();

}


function loadTasks(){

    let tasks =
    JSON.parse(
        localStorage.getItem("tasks")
    ) || [];


    let list =
    document.getElementById("taskList");


    list.innerHTML="";


    tasks.forEach(function(task,index){

        let li =
        document.createElement("li");


        li.innerHTML=`

        ${escapeHTML(task)}

        <button
        class="delete"
        onclick="deleteTask(${index})">

        ❌

        </button>

        `;


        list.appendChild(li);

    });


    document.getElementById("taskCount")
    .innerText=tasks.length;

}


function deleteTask(index){

    let tasks =
    JSON.parse(
        localStorage.getItem("tasks")
    ) || [];


    tasks.splice(index,1);


    localStorage.setItem(
        "tasks",
        JSON.stringify(tasks)
    );


    loadTasks();

}


/* ================= SEARCH ================= */

function searchAll(){

    let search =
    document
    .getElementById("search")
    .value
    .toLowerCase();


    document
    .querySelectorAll(
        ".note,.event,.homework,.pdf,.book,li"
    )
    .forEach(function(item){

        if(
            item.innerText
            .toLowerCase()
            .includes(search)
        ){

            item.style.outline =
            search
            ? "3px solid #4f46e5"
            : "none";

        }

        else{

            item.style.outline="none";

        }

    });

}


/* ================= SECURITY ================= */

function escapeHTML(text){

    return String(text)

    .replace(/&/g,"&amp;")

    .replace(/</g,"&lt;")

    .replace(/>/g,"&gt;")

    .replace(/"/g,"&quot;")

    .replace(/'/g,"&#039;");

}


function escapeAttribute(text){

    return String(text)

    .replace(/"/g,"%22")

    .replace(/</g,"%3C")

    .replace(/>/g,"%3E");

}


/* ================= LOAD DATA ================= */

loadNotes();

loadEvents();

loadHomework();

loadPDFs();

loadTasks();


</script>

</body>
</html>