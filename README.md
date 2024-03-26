### Automated_testing_Library_API_Report_with_newman

This project demonstrates API testing using Postman, providing a collection of tests to validate various endpoints of the API. 

### **Features**

- Tests for GET, POST requests
- Collection of tests covering different API endpoints
- Environment setup for easy switching between environments
- Pre-request scripts for data setup
- Test scripts for assertions and validations

## API Documentation:
- https://documenter.getpostman.com/view/31255357/2sA35D6isJ
  
### **Technology used:**
- Postman
- Newman

### **Prerequisite:**
- Node Js
- Newman
- Newman Html Report Library

### **Installation**

1. Postman: If you haven't already, [download and install Postman.](https://www.postman.com/downloads/)
2. Clone the repository:
 ```console
https://github.com/MuHIUDDIn98/Automated_testing_Library_API_Report_with_newman.git
  
```
3. Import the Postman collection:
    - Open Postman.
    - Click on the Import button.
    - Select the file from the repository.
4. Import the Postman environment:
    - In Postman, click on the gear icon in the top right corner.
    - Select **Import** and choose the file.
5. Newman and Report Installation Process:
    - Newman Install Command:
     ```console 
      npm install -g newman
    ```
    - Newman Html Report Install Command:
     ```console 
      npm install -g newman-reporter-htmlextra
    ```
### **Usage**
1. Select Environment:
    -   In Postman, select the appropriate environment (e.g., Development, Production) from the top-right dropdown.
3. Run Collection:
    -   Select the imported collection from the Collections sidebar.
    -   Click on the Runner button to open the collection runner.
    -   Select the desired environment.
    -   Click Start Test to run the collection.
8. View Results:
    -   Once the tests are complete, view the results in the Runner tab.
    -   Detailed test results can be viewed for each request.





### Generate report using CLI:
```console
newman run Library.postman_collection.json -e Library_env.postman_environment.json -r cli,htmlextra
```


<!DOCTYPE html>
<html lang="en" style="overflow-y: scroll;">
<head>
  <meta charset="UTF-8">
  <title>Newman Summary Report</title>
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.13.0/css/all.min.css">
  <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.1.3/css/bootstrap.min.css">
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/highlight.js/10.1.2/styles/default.min.css">
  <link rel="stylesheet" href="https://cdn.datatables.net/v/bs4/dt-1.10.18/datatables.min.css"/>

<style>
code.renderMarkdown table, code.renderMarkdown th, code.renderMarkdown td {
    border: 1px solid black;
    width: max-content;
    padding: .75rem;
}

.theme-dark {
    --background-color: #222;
    --bg-card-deck: #444444;
    --text-color: #ccd2d8;
    --tab-border: solid 1px #444;
    --success: #3c9372;
    --failure: #c24a3f;
    --warning: #d28c23;
    --info: #4083b6;
    --badge-outline: #3c9372;
    --badge-bg: #cdd3db;
    --badge-text: #ccd2d9;
    --failure-row: #c24a3f;
    --warning-row: #d28c23;
    --card-bg: #444;
    --card-footer: #4f5758;
    --form-input: #ececb5;
    --hov-text: #d2dae5;
    --h4-text: #ccd1d9;
}

.theme-light {
    --tab-border: solid 1px #fff;
    --text-color: #000000;
    --success: #42a745;
    --failure: #dc3544;
    --warning: #f4c10b;
    --info: #49a1b8;
    --badge-outline: #040411;
    --badge-bg: #f8f9fa;
    --badge-text: #fff;
    --failure-row: #f5c6cb;
    --warning-row: #ffeeba;
    --card-bg: #f7f7f7;
    --hov-text: #fff;
    --h4-text: #ffffff;
}

body {
  padding-top:30px;
  background-color: var(--background-color)!important;
  color: var(--text-color);
}

#execution-data {
  padding: 10px;
  border: var(--tab-border);
  border-top: none;
}

.nav-tabs {
  padding-top: 10px;
  height: 105px;
  overflow-y: auto;
}

body.theme-dark .card-header {
    background-color: #444;
}

body.theme-light .card-header {
    background-color: #f7f7f7;
}

.card-footer {
    padding: .75rem 1.25rem;
    background-color: var(--card-footer);
}

.card-deck {
    background-color: var(--bg-card-deck)!important;
}
.form-control {
    background: var(--form-input);
}

.custom-tab {
  padding: 10px 15px;
  margin-right: 0px;
  height: 47px;
  width: 69px;
  text-align: center;
  border: var(--tab-border);
  border-bottom: none;
  cursor:pointer;
}

body.theme-dark .text-white {
    color: #ccd2d9!important;
}
h4 {
    color: var(--h4-text);
}

body.theme-dark h1 {
    color: #ccd2da;
}

body.theme-dark .bg-light>td {
    background: #4f5858!important;
}

body.theme-dark .hljs {
    background: #0a0a0ab0!important;
    color: #8d8787!important;
}

.bg-info {
    background-color: var(--info)!important;
}
.bg-success {
    background-color: var(--success)!important;
}

.alert-success {
    background-color: var(--success)!important;
}

.alert-warning {
    background-color: var(--warning)!important;
}

.alert-info {
    background-color: var(--info)!important;
}

.bg-warning {
    background-color: var(--warning)!important;
}

.badge-warning {
    color: var(--badge-text)!important;
    background-color: var(--warning)!important;
}

.table-warning>td {
    background-color: var(--warning-row);
}

.alert-danger {
    background-color: var(--failure)!important;
}

body.theme-dark .alert-dark {
    background-color: #636467!important;
}

body.theme-dark .text-dark {
    color: #d1dae4!important;
}

body.theme-dark .badge-light {
    color: #212529;
    background-color: #cdd3db;
}

body.theme-light .badge-light {
    color: #212529;
    background-color: #f8f9fa;
}
body.theme-light .bg-danger {
    background-color: var(--failure)!important;
}

body.theme-dark .bg-danger {
    background-color: var(--failure)!important;
}

.table-danger>td {
    background-color: var(--failure-row);
}

body.theme-dark .table .thead-light th {
    background-color: #4f5858!important;
    border-color: #dee2e6!important;
    color: #ccd2d8!important;
}

.itPassed {
  background: var(--success);
  color: white;
}
.itFailed {
  background: var(--failure);
  color: white;
}

.resultsInfoPass {
  color: var(--success);
  padding-top: 4px;
}

.resultsInfoFail {
  color: var(--failure);
  padding-top: 4px;
}

.badge-outline-success {
  color: var(--success);
  border: 1px solid var(--success);
  background-color: transparent;
}

.badge-outline {
  color: var(--badge-outline);
  border: 1px solid var(--badge-outline);
  background-color: transparent;
}

.btn-outline-success {
    color: var(--success)!important;
    border-color: var(--success)!important;
}

.backToTop:hover {
  background-color: var(--success);
  border-color: var(--success);
  color: var(--hov-text)!important;
}

.btn-outline-success:hover {
  background-color: var(--success);
  border-color: var(--success);
  color: var(--hov-text)!important;
}

.btn-outline-secondary {
  background-color: var(--success)!important;
  color: var(--hov-text)!important;
}

body.theme-dark .env-heading {
    color: #ccd2d9!important;
}

body, html {
  height:100%;
}

.card {
  overflow:hidden;
}

body.theme-dark .card-body {
    background-color: #444;
}

body.theme-light .card-body {
    background-color: #f7f7f7;
}

body.theme-dark .card-body .bg-danger {
    background-color: var(--failure)!important;
}

body.theme-light .card-body .bg-danger {
    background-color: var(--failure)!important;
}

.card-body .rotate {
  z-index: 8;
  float: right;
  height: 100%;
}

.card-body .rotate i {
  color: #14141426;
  position: absolute;
  left: 0;
  left: auto;
  right: -10px;
  bottom: 0;
  display: block;
  -webkit-transform: rotate(-44deg);
  -moz-transform: rotate(-44deg);
  -o-transform: rotate(-44deg);
  -ms-transform: rotate(-44deg);
  transform: rotate(-44deg);
}

.dyn-height {
  max-height:350px;
  overflow-y:auto;
}

.nav-pills .nav-link.active {
  background-color: transparent!important;
}

.backToTop {
  display: none;
  position: fixed;
  bottom: 10px;
  right: 20px;
  z-index: 99;
  font-size: 15px;
  outline: none;
  cursor: pointer;
  padding: 15px;
  border-radius: 4px;
}

.card-header .fa {
  transition: .3s transform ease-in-out;
}
.card-header .collapsed .fa {
  transform: rotate(90deg);
}

.single-line-tabs {
  padding-top: 10px;
  height: 60px;
}

::-webkit-scrollbar {
  width: 5px;
}

::-webkit-scrollbar-track {
  background: #f1f1f1;
}

::-webkit-scrollbar-thumb {
  background: #888;
}

::-webkit-scrollbar-thumb:hover {
  background: #555;
}

/* The switch - the box around the slider */
.switch {
  position: relative;
  display: inline-block;
  width: 44px;
  height: 20px;
}

/* Hide default HTML checkbox */
.switch input {
  opacity: 0;
  width: 0;
  height: 0;
}

/* The slider */
.slider {
  position: absolute;
  cursor: pointer;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background-color: #ccc;
  -webkit-transition: 0.4s;
  transition: 0.4s;
}

.slider:before {
  position: absolute;
  content: "";
  height: 20px;
  width: 20px;
  left: 0px;
  bottom: 4px;
  top: 0;
  bottom: 0;
  margin: auto 0;
  -webkit-transition: 0.4s;
  transition: 0.4s;
  box-shadow: 0 0px 15px #2020203d;
  background: white;
  background-repeat: no-repeat;
  background-position: center;
}

input:checked + .slider {
  background-color: #4083b6;
}

input:focus + .slider {
  box-shadow: 0 0 1px #4083b6;
}

input:checked + .slider:before {
  -webkit-transform: translateX(24px);
  -ms-transform: translateX(24px);
  transform: translateX(24px);
  background: white;
  background-repeat: no-repeat;
  background-position: center;
}

/* Rounded sliders */
.slider.round {
  border-radius: 34px;
}

.slider.round:before {
  border-radius: 50%;
}

table.dataTable td, table.dataTable tr {
    vertical-align: middle;
}

body.theme-dark code {
    color: #ccd2d8!important;
}

body.theme-light code {
    color: #000000!important;
}

.text-wrap {
    word-wrap: break-word; 
    min-width: 600px; 
    max-width: 600px; 
    white-space: normal;
}

</style>
</head>
<body class="theme-dark">
<script>
    function setTheme(themeName) {
        localStorage.setItem('theme', themeName);
        document.body.className = themeName;
    }

    function toggleTheme() {
        if (localStorage.getItem('theme') === 'theme-light') {
            setTheme('theme-dark');
        } else {
            setTheme('theme-light');
        }
    }
</script>
  <div class="container">
        <div class="container">
            <label>Light</label>
            <label id="switch" class="switch">
                <input type="checkbox" onchange="toggleTheme()" id="slider">
                <span class="slider round"></span>
            </label>
            <label>Dark</label>
        </div>
        <div class="card">
        <div class="card-header">
            <ul class="nav nav-pills mb-3 nav-justified" id="pills-tab" role="tablist">
            <li class="nav-item bg-info active" data-toggle="tooltip" title="Click to view the Summary">
                <a class="nav-link text-white" id="pills-summary-tab" data-toggle="pill" href="#pills-summary" role="tab" aria-controls="pills-summary" aria-selected="true">Summary</a>
            </li>
            <li class="nav-item bg-success" data-toggle="tooltip" title="Click to view the Requests">
                <a class="nav-link text-white" id="pills-requests-tab" data-toggle="pill" href="#pills-requests" role="tab" aria-controls="pills-requests" aria-selected="false">Total Requests <span class="badge badge-light">20</span></a>
            </li>
            <li class="nav-item bg-danger" data-toggle="tooltip" title="Click to view the Failed Tests">
                <a class="nav-link text-white" id="pills-failed-tab" data-toggle="pill" href="#pills-failed" role="tab" aria-controls="pills-failed" aria-selected="false">Failed Tests <span class="badge badge-light">0</span></a>
            </li>
            <li class="nav-item bg-warning" data-toggle="tooltip" title="Click to view the Skipped Tests">
                <a class="nav-link text-white" id="pills-skipped-tab" data-toggle="pill" href="#pills-skipped" role="tab" aria-controls="pills-skipped" aria-selected="false">Skipped Tests <span class="badge badge-light">0</span></a>
            </li>
            </ul>
        <div class="tab-content" id="pills-tabContent">
            <div class="tab-pane fade show active" id="pills-summary" role="tabcard" aria-labelledby="pills-summary-tab">
<div class="row">
  <div class="col-md-9 col-lg-12 main">
   <h1 class="display-2 text-center">Newman Run Dashboard</h1>
   <h5 class="text-center">Monday, 25 March 2024 17:05:03</h5>
   <div class="row">
    <div class="col-lg-3 col-md-6">
     <div class="card text-white card-success">
      <div class="card-body bg-success">
       <div class="rotate">
        <i class="fa fa-retweet fa-5x"></i>
       </div>
       <h6 class="text-uppercase">Total Iterations</h6>
       <h1 class="display-1">5</h1>
      </div>
     </div>
    </div>
    <div class="col-lg-3 col-md-6">
     <div class="card text-white card-danger">
      <div class="card-body bg-success">
       <div class="rotate">
        <i class="fa fa-list fa-4x"></i>
       </div>
       <h6 class="text-uppercase">Total Assertions</h6>
       <h1 class="display-1">45</h1>
      </div>
     </div>
    </div>
    <div class="col-lg-3 col-md-6">
     <div class="card text-white card-info">
      <div class="card-body bg-success">
       <div class="rotate">
        <i class="fa fa-plus-circle fa-5x"></i>
       </div>
       <h6 class="text-uppercase">Total Failed Tests</h6>
       <h1 class="display-1">0</h1>
      </div>
     </div>
    </div>
    <div class="col-lg-3 col-md-6">
     <div class="card text-white card-warning">
      <div class="card-body bg-success">
       <div class="rotate">
        <i class="fa fa-share fa-5x"></i>
       </div>
       <h6 class="text-uppercase">Total Skipped Tests</h6>
       <h1 class="display-1">0</h1>
      </div>
     </div>
    </div>
   </div>
   <hr>
    <div class="row">
    <div class="col">
        <div class="row">
        <div class="col-sm-12 mb-3">
            <div class="card border-info">
                <div class="card-body">
                <h5 class="card-title text-uppercase text-white text-center bg-info">File Information</h5>
                <span><i class="fas fa-file-code"></i></span><strong> Collection:</strong> Library<br>
                
                <span><i class="fas fa-file-code"></i></span><strong> Environment:</strong> Library_env<br>
                </div>
            </div>
        </div>
        </div>
        <div class="row">
        <div class="col-sm-12 mb-3">
            <div class="card border-info">
                <div class="card-body">
                <h5 class="card-title text-uppercase text-white text-center bg-info">Timings and Data</h5>
                <span><i class="fas fa-stopwatch"></i></span><strong> Total run duration:</strong> 4.2s<br>
                <span><i class="fas fa-database"></i></span><strong> Total data received:</strong> 1.24KB<br>
                <span><i class="fas fa-stopwatch"></i></span><strong> Average response time:</strong> 121ms<br>
                </div>
            </div>
        </div>
        </div>
        <div class="row">
        <div class="col-sm-12 mb-3">
            <div class="table-responsive">
            <table class="table table-striped table-bordered">
                <thead class="thead-inverse">
                    <tr class="text-center">
                        <th class="text-uppercase">Summary Item</th>
                        <th class="text-uppercase">Total</th>
                        <th class="text-uppercase">Failed</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td>Requests</td>
                        <td class="text-center">20</td>
                        <td class="text-center">0</td>
                    </tr>
                    <tr>
                        <td>Prerequest Scripts</td>
                        <td class="text-center">25</td>
                        <td class="text-center">0</td>
                    </tr>
                    <tr>
                        <td>Test Scripts</td>
                        <td class="text-center">35</td>
                        <td class="text-center">0</td>
                    </tr>
                    <tr class="">
                        <td>Assertions</td>
                        <td class="text-center">45</td>
                        <td class="text-center">0</td>
                    </tr>
                    <tr class="">
                        <td>Skipped Tests</td>
                        <td class="text-center">0</td>
                        <td class="text-center">-</td>
                    </tr>
                </tbody>
            </table>
            </div>
        </div>
        </div>
    <hr>
   </div>
   </div>
  </div>
 </div>
        </div>
            <div class="tab-pane fade" id="pills-failed" role="tabcard" aria-labelledby="pills-failed-tab">
                <button id="topOfFailuresScreen" class="btn btn-outline-success btn-sm backToTop" onclick="topFunction()">Go To Top</button>

                <div class="alert alert-success text-uppercase text-center">
                     <br><br><h1 class="text-center">There are no failed tests <span><i class="far fa-thumbs-up"></i></span></h1><br><br>
                </div>
            </div>

            <div class="tab-pane fade" id="pills-skipped" role="tabcard" aria-labelledby="pills-skipped-tab">
                <button id="topOfSkippedScreen" class="btn btn-outline-success btn-sm backToTop" onclick="topFunction()">Go To Top</button>

                <div class="alert alert-success text-uppercase text-center">
                    <br><br><h1 class="text-center">There are no skipped tests <span><i class="far fa-thumbs-up"></i></span></h1><br><br>
                </div>
            </div>
            <div class="tab-pane fade" id="pills-requests" role="tabcard" aria-labelledby="pills-requests-tab">

            <button id="topOfRequestsScreen" class="btn btn-outline-success btn-sm backToTop" onclick="topFunction()">Go To Top</button>

            <div class="btn-group float-right" role="group" aria-label="Button Group">
                <button id="openAll" class="btn btn-outline-success btn-sm float-right" style="text-align: center; width: 140px;">Expand Folders</button>
                <button id="openAllRequests" class="btn btn-outline-success btn-sm float-right" style="text-align: center; width: 140px;">Expand Requests</button>
            </div>

    <div class="text-uppercase" id="execution-menu">
        <h5>5 Iterations available to view</h5>
        
        <nav class="table-responsive">
        <ul class="nav single-line-tabs" id="iterationList">
        </ul>
        </nav>
    </div>
    <h6 class="text-uppercase text-muted" id="iterationSelected" style="padding-top: 10px;"></h6>
	<div class="tab-content" id="execution-data">
            <div id="folder-39195611-8f6b-40de-b7a3-b0890ae57d82" class="card-deck iteration-0">
            <div class="row iteration-0">
                <div class="col-sm-12 mb-3 iteration-0">
                <div class="card iteration-0">
                    <div class="card-header  bg-success iteration-0">
                        <a data-toggle="collapse" href="#" data-target="#collapse-39195611-8f6b-40de-b7a3-b0890ae57d82" aria-expanded="false" aria-controls="collapse" id="requests-39195611-8f6b-40de-b7a3-b0890ae57d82" class="collapsed text-white z-block">
                    Iteration: 1 - AddBook <i class="float-lg-right fa fa-chevron-down" style="padding-top: 5px;"></i>
                </a>
                    </div>
                    <div id="collapse-39195611-8f6b-40de-b7a3-b0890ae57d82" class="collapse" aria-labelledby="requests-39195611-8f6b-40de-b7a3-b0890ae57d82">
                    <div class="card-body">
                        <div class="row">
                            <div class="col-sm-12 mb-3">
                                <div class="card-deck">
                                <div class="card border-info" style="width: 50rem;">
                                    <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Request Information</h5>
                                    <span><i class="fas fa-info-circle"></i></span><strong> Request Method:</strong> <span class="badge-outline-success badge badge-success"> GET</span><br>
                                    <span><i class="fas fa-info-circle"></i></span><strong> Request URL:</strong> <a href="https://rahulshettyacademy.com/Library/Addbook.php" target="_blank">https://rahulshettyacademy.com/Library/Addbook.php</a><br>
                                    </div>
                                </div>
                                <div class="card border-info" style="width: 50rem;">
                                    <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Response Information</h5>
                                    <span><i class="fas fa-info-circle"></i></span><strong> Response Code:</strong> <span class="float-right badge-outline badge badge-success"> 200 - OK</span><br>
                                    <span><i class="fas fa-stopwatch"></i></span><strong> Mean time per request:</strong> <span class="float-right badge-outline badge badge-success"> 353ms</span><br>
                                    <span><i class="fas fa-database"></i></span><strong> Mean size per request:</strong> <span class="float-right badge-outline badge badge-success"> 44B</span><br>
                                    <hr>
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Test Pass Percentage</h5>
                                    <div>
                                        <div class="progress" style="height: 40px;">
                                            <div class="progress-bar  bg-success" style="width: 100%" role="progressbar">
                                            <h5 style="padding-top:5px;"><strong>100 %</strong></h5>
                                            </div>
                                        </div>
                                    </div>
                                    </div>
                                </div>
                            </div>
                            </div>
                        </div>
                        <div class="row">
                            <div class="col-sm-12 mb-3">
                                <div class="card-deck">
                                <div class="card border-info" style="width: 50rem;">
                                    <div class="card-body">
                                        <h5 class="card-title text-uppercase text-white text-center bg-info">Request Headers</h5>
                                        <div class="table-responsive">
                                            <table class="table table-bordered">
                                            <thead class="thead-light text-center"><tr><th>Header Name</th><th>Header Value</th></tr></thead>
                                                <tbody>
                                                    <tr>
                                                        <td class="text-nowrap">Content-Type</td>
                                                        <td class="text-wrap">application/json</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">User-Agent</td>
                                                        <td class="text-wrap">PostmanRuntime/7.37.1</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Accept</td>
                                                        <td class="text-wrap">*/*</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Cache-Control</td>
                                                        <td class="text-wrap">no-cache</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Postman-Token</td>
                                                        <td class="text-wrap">550faf13-bfa7-4d4d-9c5c-a4c3e0114123</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Host</td>
                                                        <td class="text-wrap">rahulshettyacademy.com</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Accept-Encoding</td>
                                                        <td class="text-wrap">gzip, deflate, br</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Connection</td>
                                                        <td class="text-wrap">keep-alive</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Content-Length</td>
                                                        <td class="text-wrap">111</td>
                                                    </tr>
                                                </tbody>
                                            </table>
                                        </div>
                                    </div>
                                </div>
                                </div>
                            </div>
                        </div>
                        <div class="row">
                        <div class="col-sm-12 mb-3">
                            <div class="card-deck">
                            <div class="card border-info" style="width: 50rem;">
                                <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Request Body</h5>
                                        <div class="dyn-height">
                                            <pre><code id="copyReqText-0" class="prettyPrint">{
        
        &quot;name&quot;:&quot;Python for Ethical Hacking&quot;,
        &quot;isbn&quot;:&quot;YC277&quot;,
        &quot;aisle&quot;:&quot;917&quot;,
        &quot;author&quot;:&quot;Stephania Hegmann&quot;
        }
        
        </code></pre>
                                        </div>
                                        <div class="card-footer">
                                            <button class="btn btn-outline-secondary btn-sm copyButton" type="button" data-clipboard-action="copy" data-clipboard-target="#copyReqText-0">Copy to Clipboard</button>
                                        </div>
                                </div>
                            </div>
                            </div>
                        </div>
                        </div>
                        <div class="row">
                        <div class="col-sm-12 mb-3">
                            <div class="card-deck">
                            <div class="card border-info" style="width: 50rem;">
                                <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Response Headers</h5>
                                    <div class="table-responsive">
                                        <table class="table table-bordered">
                                        <thead class="thead-light text-center"><tr><th>Header Name</th><th>Header Value</th></tr></thead>
                                            <tbody>
                                                <tr>
                                                    <td class="text-nowrap">Date</td>
                                                    <td class="text-wrap">Mon, 25 Mar 2024 11:05:00 GMT</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Server</td>
                                                    <td class="text-wrap">Apache/2.4.52 (Ubuntu)</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Access-Control-Allow-Origin</td>
                                                    <td class="text-wrap">*</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Access-Control-Allow-Methods</td>
                                                    <td class="text-wrap">POST</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Access-Control-Max-Age</td>
                                                    <td class="text-wrap">3600</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Access-Control-Allow-Headers</td>
                                                    <td class="text-wrap">Content-Type, Access-Control-Allow-Headers, Authorization, X-Requested-With</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Content-Length</td>
                                                    <td class="text-wrap">44</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Keep-Alive</td>
                                                    <td class="text-wrap">timeout&#x3D;5, max&#x3D;100</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Connection</td>
                                                    <td class="text-wrap">Keep-Alive</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Content-Type</td>
                                                    <td class="text-wrap">application/json;charset&#x3D;UTF-8</td>
                                                </tr>
                                            </tbody>
                                        </table>
                                    </div>
                                </div>
                            </div>
                            </div>
                        </div>
                        </div>
                        <div class="row">
                        <div class="col-sm-12 mb-3">
                            <div class="card-deck">
                            <div class="card border-info" style="width: 50rem;">
                                <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Response Body</h5>
                                        <div class="dyn-height">
                                                <pre><code id="copyText-cc6d406a-a829-4cde-b988-3df674dae181" class="prettyPrint">{&quot;Msg&quot;:&quot;successfully added&quot;,&quot;ID&quot;:&quot;YC277917&quot;}</code></pre>
                                        </div>
                                        <div class="card-footer">
                                            <button class="btn btn-outline-secondary btn-sm copyButton" type="button" data-clipboard-action="copy" data-clipboard-target="#copyText-cc6d406a-a829-4cde-b988-3df674dae181">Copy to Clipboard</button>
                                        </div>
                                </div>
                            </div>
                            </div>
                            </div>
                        </div>
                        <div class="row">
                            <div class="card border-info">
                                <div class="card-body">
                                <h5 class="card-title text-uppercase text-white text-center bg-info">Test Information</h5>
                                    <div class="table-responsive text-nowrap">
                                        <table class="datatable table table-hover">
                                        <thead><tr class="text-center"><th>Name</th><th>Passed</th><th>Failed</th><th>Skipped</th></tr></thead>
                                            <tbody>
                                                <tr >
                                                    <td >Validation of status code 200</td>
                                                    <td class="text-center bg-success">1</td>
                                                    <td class="text-center ">0</td>
                                                    <td class="text-center ">0</td>
                                                </tr>
                                                <tr >
                                                    <td >Validation of response jason schema</td>
                                                    <td class="text-center bg-success">1</td>
                                                    <td class="text-center ">0</td>
                                                    <td class="text-center ">0</td>
                                                </tr>
                                                <tr >
                                                    <td >validation of successfully added</td>
                                                    <td class="text-center bg-success">1</td>
                                                    <td class="text-center ">0</td>
                                                    <td class="text-center ">0</td>
                                                </tr>
                                                <tr >
                                                    <td >Validation of Respose time below 1600</td>
                                                    <td class="text-center bg-success">1</td>
                                                    <td class="text-center ">0</td>
                                                    <td class="text-center ">0</td>
                                                </tr>
                                            </tbody>
                                            <tfoot>
                                                <tr class="bg-light">
                                                    <td><strong>Total</strong></td>
                                                    <td class="text-center">4</td>
                                                    <td class="text-center">0</td>
                                                    <td class="text-center">0</td>
                                                </tr>
                                            </tfoot>
                                        </table>
                                    </div>
                                    <div class="row d-none">
                                    <div class="col-sm-12 mb-3">
                                        <div class="card-deck">
                                        <div class="card border-danger" style="width: 50rem;">
                                            <div class="card-body">
                                                <h5 class="card-title text-uppercase text-white text-center bg-danger">Test Failure</h5>
                                                <div class="table-responsive">
                                                    <table class="table table-hover">
                                                    <thead><tr class="text-nowrap"><th>Test Name</th><th>Assertion Error</th></tr></thead>
                                                        <tbody>
                                                        </tbody>
                                                    </table>
                                                </div>
                                            </div>
                                        </div>
                                        </div>
                                    </div>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                    </div>
                </div>
                </div>
            </div>
            </div>
            <div id="folder-6ee48502-c146-4da3-b82f-d978307eccc5" class="card-deck iteration-0">
            <div class="row iteration-0">
                <div class="col-sm-12 mb-3 iteration-0">
                <div class="card iteration-0">
                    <div class="card-header  bg-success iteration-0">
                        <a data-toggle="collapse" href="#" data-target="#collapse-6ee48502-c146-4da3-b82f-d978307eccc5" aria-expanded="false" aria-controls="collapse" id="requests-6ee48502-c146-4da3-b82f-d978307eccc5" class="collapsed text-white z-block">
                    Iteration: 1 - GetBookByID <i class="float-lg-right fa fa-chevron-down" style="padding-top: 5px;"></i>
                </a>
                    </div>
                    <div id="collapse-6ee48502-c146-4da3-b82f-d978307eccc5" class="collapse" aria-labelledby="requests-6ee48502-c146-4da3-b82f-d978307eccc5">
                    <div class="card-body">
                        <div class="row">
                            <div class="col-sm-12 mb-3">
                                <div class="card-deck">
                                <div class="card border-info" style="width: 50rem;">
                                    <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Request Information</h5>
                                    <span><i class="fas fa-info-circle"></i></span><strong> Request Method:</strong> <span class="badge-outline-success badge badge-success"> GET</span><br>
                                    <span><i class="fas fa-info-circle"></i></span><strong> Request URL:</strong> <a href="https://rahulshettyacademy.com/Library/GetBook.php?ID&#x3D;YC277917" target="_blank">https://rahulshettyacademy.com/Library/GetBook.php?ID&#x3D;YC277917</a><br>
                                    </div>
                                </div>
                                <div class="card border-info" style="width: 50rem;">
                                    <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Response Information</h5>
                                    <span><i class="fas fa-info-circle"></i></span><strong> Response Code:</strong> <span class="float-right badge-outline badge badge-success"> 200 - OK</span><br>
                                    <span><i class="fas fa-stopwatch"></i></span><strong> Mean time per request:</strong> <span class="float-right badge-outline badge badge-success"> 91ms</span><br>
                                    <span><i class="fas fa-database"></i></span><strong> Mean size per request:</strong> <span class="float-right badge-outline badge badge-success"> 102B</span><br>
                                    <hr>
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Test Pass Percentage</h5>
                                    <div>
                                        <div class="progress" style="height: 40px;">
                                            <div class="progress-bar  bg-success" style="width: 100%" role="progressbar">
                                            <h5 style="padding-top:5px;"><strong>100 %</strong></h5>
                                            </div>
                                        </div>
                                    </div>
                                    </div>
                                </div>
                            </div>
                            </div>
                        </div>
                        <div class="row">
                            <div class="col-sm-12 mb-3">
                                <div class="card-deck">
                                <div class="card border-info" style="width: 50rem;">
                                    <div class="card-body">
                                        <h5 class="card-title text-uppercase text-white text-center bg-info">Request Headers</h5>
                                        <div class="table-responsive">
                                            <table class="table table-bordered">
                                            <thead class="thead-light text-center"><tr><th>Header Name</th><th>Header Value</th></tr></thead>
                                                <tbody>
                                                    <tr>
                                                        <td class="text-nowrap">User-Agent</td>
                                                        <td class="text-wrap">PostmanRuntime/7.37.1</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Accept</td>
                                                        <td class="text-wrap">*/*</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Cache-Control</td>
                                                        <td class="text-wrap">no-cache</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Postman-Token</td>
                                                        <td class="text-wrap">1a579456-42e9-4180-a065-988e199500a0</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Host</td>
                                                        <td class="text-wrap">rahulshettyacademy.com</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Accept-Encoding</td>
                                                        <td class="text-wrap">gzip, deflate, br</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Connection</td>
                                                        <td class="text-wrap">keep-alive</td>
                                                    </tr>
                                                </tbody>
                                            </table>
                                        </div>
                                    </div>
                                </div>
                                </div>
                            </div>
                        </div>
                        <div class="row">
                        <div class="col-sm-12 mb-3">
                            <div class="card-deck">
                            <div class="card border-info" style="width: 50rem;">
                                <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Response Headers</h5>
                                    <div class="table-responsive">
                                        <table class="table table-bordered">
                                        <thead class="thead-light text-center"><tr><th>Header Name</th><th>Header Value</th></tr></thead>
                                            <tbody>
                                                <tr>
                                                    <td class="text-nowrap">Date</td>
                                                    <td class="text-wrap">Mon, 25 Mar 2024 11:05:00 GMT</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Server</td>
                                                    <td class="text-wrap">Apache/2.4.52 (Ubuntu)</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Access-Control-Allow-Origin</td>
                                                    <td class="text-wrap">*</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Access-Control-Allow-Methods</td>
                                                    <td class="text-wrap">POST</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Access-Control-Max-Age</td>
                                                    <td class="text-wrap">3600</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Access-Control-Allow-Headers</td>
                                                    <td class="text-wrap">Content-Type, Access-Control-Allow-Headers, Authorization, X-Requested-With</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Content-Length</td>
                                                    <td class="text-wrap">102</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Keep-Alive</td>
                                                    <td class="text-wrap">timeout&#x3D;5, max&#x3D;99</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Connection</td>
                                                    <td class="text-wrap">Keep-Alive</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Content-Type</td>
                                                    <td class="text-wrap">application/json;charset&#x3D;UTF-8</td>
                                                </tr>
                                            </tbody>
                                        </table>
                                    </div>
                                </div>
                            </div>
                            </div>
                        </div>
                        </div>
                        <div class="row">
                        <div class="col-sm-12 mb-3">
                            <div class="card-deck">
                            <div class="card border-info" style="width: 50rem;">
                                <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Response Body</h5>
                                        <div class="dyn-height">
                                                <pre><code id="copyText-909a8cbf-6e67-4645-87b1-f46ac9717948" class="prettyPrint">[{&quot;book_name&quot;:&quot;Python for Ethical Hacking&quot;,&quot;isbn&quot;:&quot;YC277&quot;,&quot;aisle&quot;:&quot;917&quot;,&quot;author&quot;:&quot;Stephania Hegmann&quot;}]</code></pre>
                                        </div>
                                        <div class="card-footer">
                                            <button class="btn btn-outline-secondary btn-sm copyButton" type="button" data-clipboard-action="copy" data-clipboard-target="#copyText-909a8cbf-6e67-4645-87b1-f46ac9717948">Copy to Clipboard</button>
                                        </div>
                                </div>
                            </div>
                            </div>
                            </div>
                        </div>
                        <div class="row">
                            <div class="card border-info">
                                <div class="card-body">
                                <h5 class="card-title text-uppercase text-white text-center bg-info">Test Information</h5>
                                    <div class="table-responsive text-nowrap">
                                        <table class="datatable table table-hover">
                                        <thead><tr class="text-center"><th>Name</th><th>Passed</th><th>Failed</th><th>Skipped</th></tr></thead>
                                            <tbody>
                                                <tr >
                                                    <td >Validation of status code 200</td>
                                                    <td class="text-center bg-success">1</td>
                                                    <td class="text-center ">0</td>
                                                    <td class="text-center ">0</td>
                                                </tr>
                                                <tr >
                                                    <td >Validation of response jason schema</td>
                                                    <td class="text-center bg-success">1</td>
                                                    <td class="text-center ">0</td>
                                                    <td class="text-center ">0</td>
                                                </tr>
                                                <tr >
                                                    <td >validation of  aisle and Author name </td>
                                                    <td class="text-center bg-success">1</td>
                                                    <td class="text-center ">0</td>
                                                    <td class="text-center ">0</td>
                                                </tr>
                                            </tbody>
                                            <tfoot>
                                                <tr class="bg-light">
                                                    <td><strong>Total</strong></td>
                                                    <td class="text-center">3</td>
                                                    <td class="text-center">0</td>
                                                    <td class="text-center">0</td>
                                                </tr>
                                            </tfoot>
                                        </table>
                                    </div>
                                    <div class="row d-none">
                                    <div class="col-sm-12 mb-3">
                                        <div class="card-deck">
                                        <div class="card border-danger" style="width: 50rem;">
                                            <div class="card-body">
                                                <h5 class="card-title text-uppercase text-white text-center bg-danger">Test Failure</h5>
                                                <div class="table-responsive">
                                                    <table class="table table-hover">
                                                    <thead><tr class="text-nowrap"><th>Test Name</th><th>Assertion Error</th></tr></thead>
                                                        <tbody>
                                                        </tbody>
                                                    </table>
                                                </div>
                                            </div>
                                        </div>
                                        </div>
                                    </div>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                    </div>
                </div>
                </div>
            </div>
            </div>
            <div id="folder-c944e98b-5b4d-4bcf-b10e-b13dab6b891f" class="card-deck iteration-0">
            <div class="row iteration-0">
                <div class="col-sm-12 mb-3 iteration-0">
                <div class="card iteration-0">
                    <div class="card-header  bg-success iteration-0">
                        <a data-toggle="collapse" href="#" data-target="#collapse-c944e98b-5b4d-4bcf-b10e-b13dab6b891f" aria-expanded="false" aria-controls="collapse" id="requests-c944e98b-5b4d-4bcf-b10e-b13dab6b891f" class="collapsed text-white z-block">
                    Iteration: 1 - GetBookByAuthor <i class="float-lg-right fa fa-chevron-down" style="padding-top: 5px;"></i>
                </a>
                    </div>
                    <div id="collapse-c944e98b-5b4d-4bcf-b10e-b13dab6b891f" class="collapse" aria-labelledby="requests-c944e98b-5b4d-4bcf-b10e-b13dab6b891f">
                    <div class="card-body">
                        <div class="row">
                            <div class="col-sm-12 mb-3">
                                <div class="card-deck">
                                <div class="card border-info" style="width: 50rem;">
                                    <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Request Information</h5>
                                    <span><i class="fas fa-info-circle"></i></span><strong> Request Method:</strong> <span class="badge-outline-success badge badge-success"> GET</span><br>
                                    <span><i class="fas fa-info-circle"></i></span><strong> Request URL:</strong> <a href="https://rahulshettyacademy.com/Library/GetBook.php?AuthorName&#x3D;Stephania%20Hegmann" target="_blank">https://rahulshettyacademy.com/Library/GetBook.php?AuthorName&#x3D;Stephania%20Hegmann</a><br>
                                    </div>
                                </div>
                                <div class="card border-info" style="width: 50rem;">
                                    <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Response Information</h5>
                                    <span><i class="fas fa-info-circle"></i></span><strong> Response Code:</strong> <span class="float-right badge-outline badge badge-success"> 200 - OK</span><br>
                                    <span><i class="fas fa-stopwatch"></i></span><strong> Mean time per request:</strong> <span class="float-right badge-outline badge badge-success"> 180ms</span><br>
                                    <span><i class="fas fa-database"></i></span><strong> Mean size per request:</strong> <span class="float-right badge-outline badge badge-success"> 73B</span><br>
                                    <hr>
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Test Pass Percentage</h5>
                                    <div>
                                        <div class="progress" style="height: 40px;">
                                            <div class="progress-bar bg-success" style="width: 100%" role="progressbar">
                                            <h5 class="text-uppercase text-white text-center" style="padding-top:5px;"><strong>No Tests for this request</strong></h5>
                                            </div>
                                        </div>
                                    </div>
                                    </div>
                                </div>
                            </div>
                            </div>
                        </div>
                        <div class="row">
                            <div class="col-sm-12 mb-3">
                                <div class="card-deck">
                                <div class="card border-info" style="width: 50rem;">
                                    <div class="card-body">
                                        <h5 class="card-title text-uppercase text-white text-center bg-info">Request Headers</h5>
                                        <div class="table-responsive">
                                            <table class="table table-bordered">
                                            <thead class="thead-light text-center"><tr><th>Header Name</th><th>Header Value</th></tr></thead>
                                                <tbody>
                                                    <tr>
                                                        <td class="text-nowrap">User-Agent</td>
                                                        <td class="text-wrap">PostmanRuntime/7.37.1</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Accept</td>
                                                        <td class="text-wrap">*/*</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Cache-Control</td>
                                                        <td class="text-wrap">no-cache</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Postman-Token</td>
                                                        <td class="text-wrap">d1e70a3a-4473-47b5-b685-beb9453a33d0</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Host</td>
                                                        <td class="text-wrap">rahulshettyacademy.com</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Accept-Encoding</td>
                                                        <td class="text-wrap">gzip, deflate, br</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Connection</td>
                                                        <td class="text-wrap">keep-alive</td>
                                                    </tr>
                                                </tbody>
                                            </table>
                                        </div>
                                    </div>
                                </div>
                                </div>
                            </div>
                        </div>
                        <div class="row">
                        <div class="col-sm-12 mb-3">
                            <div class="card-deck">
                            <div class="card border-info" style="width: 50rem;">
                                <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Response Headers</h5>
                                    <div class="table-responsive">
                                        <table class="table table-bordered">
                                        <thead class="thead-light text-center"><tr><th>Header Name</th><th>Header Value</th></tr></thead>
                                            <tbody>
                                                <tr>
                                                    <td class="text-nowrap">Date</td>
                                                    <td class="text-wrap">Mon, 25 Mar 2024 11:05:00 GMT</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Server</td>
                                                    <td class="text-wrap">Apache/2.4.52 (Ubuntu)</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Access-Control-Allow-Origin</td>
                                                    <td class="text-wrap">*</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Access-Control-Allow-Methods</td>
                                                    <td class="text-wrap">POST</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Access-Control-Max-Age</td>
                                                    <td class="text-wrap">3600</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Access-Control-Allow-Headers</td>
                                                    <td class="text-wrap">Content-Type, Access-Control-Allow-Headers, Authorization, X-Requested-With</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Content-Length</td>
                                                    <td class="text-wrap">73</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Keep-Alive</td>
                                                    <td class="text-wrap">timeout&#x3D;5, max&#x3D;98</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Connection</td>
                                                    <td class="text-wrap">Keep-Alive</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Content-Type</td>
                                                    <td class="text-wrap">application/json;charset&#x3D;UTF-8</td>
                                                </tr>
                                            </tbody>
                                        </table>
                                    </div>
                                </div>
                            </div>
                            </div>
                        </div>
                        </div>
                        <div class="row">
                        <div class="col-sm-12 mb-3">
                            <div class="card-deck">
                            <div class="card border-info" style="width: 50rem;">
                                <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Response Body</h5>
                                        <div class="dyn-height">
                                                <pre><code id="copyText-ac5ed8e1-a353-4a87-96f4-eed7aa1a66d6" class="prettyPrint">[{&quot;book_name&quot;:&quot;Python for Ethical Hacking&quot;,&quot;isbn&quot;:&quot;YC277&quot;,&quot;aisle&quot;:&quot;917&quot;}]</code></pre>
                                        </div>
                                        <div class="card-footer">
                                            <button class="btn btn-outline-secondary btn-sm copyButton" type="button" data-clipboard-action="copy" data-clipboard-target="#copyText-ac5ed8e1-a353-4a87-96f4-eed7aa1a66d6">Copy to Clipboard</button>
                                        </div>
                                </div>
                            </div>
                            </div>
                            </div>
                        </div>
                        <div class="row">
                            <div class="card border-info">
                                <div class="card-body">
                                <h5 class="card-title text-uppercase text-white text-center bg-info">Test Information</h5>
                                    <h5 class="alert alert-success text-uppercase text-center">No Tests for this request</h5>
                                </div>
                            </div>
                        </div>
                    </div>
                    </div>
                </div>
                </div>
            </div>
            </div>
            <div id="folder-19f23f22-f53f-4a0b-8f0f-38c012772a51" class="card-deck iteration-0">
            <div class="row iteration-0">
                <div class="col-sm-12 mb-3 iteration-0">
                <div class="card iteration-0">
                    <div class="card-header  bg-success iteration-0">
                        <a data-toggle="collapse" href="#" data-target="#collapse-19f23f22-f53f-4a0b-8f0f-38c012772a51" aria-expanded="false" aria-controls="collapse" id="requests-19f23f22-f53f-4a0b-8f0f-38c012772a51" class="collapsed text-white z-block">
                    Iteration: 1 - DeleteBookByID <i class="float-lg-right fa fa-chevron-down" style="padding-top: 5px;"></i>
                </a>
                    </div>
                    <div id="collapse-19f23f22-f53f-4a0b-8f0f-38c012772a51" class="collapse" aria-labelledby="requests-19f23f22-f53f-4a0b-8f0f-38c012772a51">
                    <div class="card-body">
                        <div class="row">
                            <div class="col-sm-12 mb-3">
                                <div class="card-deck">
                                <div class="card border-info" style="width: 50rem;">
                                    <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Request Information</h5>
                                    <span><i class="fas fa-info-circle"></i></span><strong> Request Method:</strong> <span class="badge-outline-success badge badge-success"> POST</span><br>
                                    <span><i class="fas fa-info-circle"></i></span><strong> Request URL:</strong> <a href="https://rahulshettyacademy.com/Library/DeleteBook.php" target="_blank">https://rahulshettyacademy.com/Library/DeleteBook.php</a><br>
                                    </div>
                                </div>
                                <div class="card border-info" style="width: 50rem;">
                                    <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Response Information</h5>
                                    <span><i class="fas fa-info-circle"></i></span><strong> Response Code:</strong> <span class="float-right badge-outline badge badge-success"> 200 - OK</span><br>
                                    <span><i class="fas fa-stopwatch"></i></span><strong> Mean time per request:</strong> <span class="float-right badge-outline badge badge-success"> 101ms</span><br>
                                    <span><i class="fas fa-database"></i></span><strong> Mean size per request:</strong> <span class="float-right badge-outline badge badge-success"> 38B</span><br>
                                    <hr>
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Test Pass Percentage</h5>
                                    <div>
                                        <div class="progress" style="height: 40px;">
                                            <div class="progress-bar  bg-success" style="width: 100%" role="progressbar">
                                            <h5 style="padding-top:5px;"><strong>100 %</strong></h5>
                                            </div>
                                        </div>
                                    </div>
                                    </div>
                                </div>
                            </div>
                            </div>
                        </div>
                        <div class="row">
                            <div class="col-sm-12 mb-3">
                                <div class="card-deck">
                                <div class="card border-info" style="width: 50rem;">
                                    <div class="card-body">
                                        <h5 class="card-title text-uppercase text-white text-center bg-info">Request Headers</h5>
                                        <div class="table-responsive">
                                            <table class="table table-bordered">
                                            <thead class="thead-light text-center"><tr><th>Header Name</th><th>Header Value</th></tr></thead>
                                                <tbody>
                                                    <tr>
                                                        <td class="text-nowrap">Content-Type</td>
                                                        <td class="text-wrap">application/json</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">User-Agent</td>
                                                        <td class="text-wrap">PostmanRuntime/7.37.1</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Accept</td>
                                                        <td class="text-wrap">*/*</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Cache-Control</td>
                                                        <td class="text-wrap">no-cache</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Postman-Token</td>
                                                        <td class="text-wrap">4cc62b58-dca4-4794-902a-3a8e4bccb91d</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Host</td>
                                                        <td class="text-wrap">rahulshettyacademy.com</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Accept-Encoding</td>
                                                        <td class="text-wrap">gzip, deflate, br</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Connection</td>
                                                        <td class="text-wrap">keep-alive</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Content-Length</td>
                                                        <td class="text-wrap">30</td>
                                                    </tr>
                                                </tbody>
                                            </table>
                                        </div>
                                    </div>
                                </div>
                                </div>
                            </div>
                        </div>
                        <div class="row">
                        <div class="col-sm-12 mb-3">
                            <div class="card-deck">
                            <div class="card border-info" style="width: 50rem;">
                                <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Request Body</h5>
                                        <div class="dyn-height">
                                            <pre><code id="copyReqText-3" class="prettyPrint">{
        
        &quot;ID&quot; : &quot;YC277917&quot;
         
        }
        </code></pre>
                                        </div>
                                        <div class="card-footer">
                                            <button class="btn btn-outline-secondary btn-sm copyButton" type="button" data-clipboard-action="copy" data-clipboard-target="#copyReqText-3">Copy to Clipboard</button>
                                        </div>
                                </div>
                            </div>
                            </div>
                        </div>
                        </div>
                        <div class="row">
                        <div class="col-sm-12 mb-3">
                            <div class="card-deck">
                            <div class="card border-info" style="width: 50rem;">
                                <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Response Headers</h5>
                                    <div class="table-responsive">
                                        <table class="table table-bordered">
                                        <thead class="thead-light text-center"><tr><th>Header Name</th><th>Header Value</th></tr></thead>
                                            <tbody>
                                                <tr>
                                                    <td class="text-nowrap">Date</td>
                                                    <td class="text-wrap">Mon, 25 Mar 2024 11:05:00 GMT</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Server</td>
                                                    <td class="text-wrap">Apache/2.4.52 (Ubuntu)</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Access-Control-Allow-Origin</td>
                                                    <td class="text-wrap">*</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Access-Control-Allow-Methods</td>
                                                    <td class="text-wrap">POST</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Access-Control-Max-Age</td>
                                                    <td class="text-wrap">3600</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Access-Control-Allow-Headers</td>
                                                    <td class="text-wrap">Content-Type, Access-Control-Allow-Headers, Authorization, X-Requested-With</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Content-Length</td>
                                                    <td class="text-wrap">38</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Keep-Alive</td>
                                                    <td class="text-wrap">timeout&#x3D;5, max&#x3D;97</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Connection</td>
                                                    <td class="text-wrap">Keep-Alive</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Content-Type</td>
                                                    <td class="text-wrap">application/json;charset&#x3D;UTF-8</td>
                                                </tr>
                                            </tbody>
                                        </table>
                                    </div>
                                </div>
                            </div>
                            </div>
                        </div>
                        </div>
                        <div class="row">
                        <div class="col-sm-12 mb-3">
                            <div class="card-deck">
                            <div class="card border-info" style="width: 50rem;">
                                <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Response Body</h5>
                                        <div class="dyn-height">
                                                <pre><code id="copyText-30e9c746-68d6-477c-b5b4-e99c496819dc" class="prettyPrint">{&quot;msg&quot;:&quot;book is successfully deleted&quot;}</code></pre>
                                        </div>
                                        <div class="card-footer">
                                            <button class="btn btn-outline-secondary btn-sm copyButton" type="button" data-clipboard-action="copy" data-clipboard-target="#copyText-30e9c746-68d6-477c-b5b4-e99c496819dc">Copy to Clipboard</button>
                                        </div>
                                </div>
                            </div>
                            </div>
                            </div>
                        </div>
                        <div class="row">
                            <div class="card border-info">
                                <div class="card-body">
                                <h5 class="card-title text-uppercase text-white text-center bg-info">Test Information</h5>
                                    <div class="table-responsive text-nowrap">
                                        <table class="datatable table table-hover">
                                        <thead><tr class="text-center"><th>Name</th><th>Passed</th><th>Failed</th><th>Skipped</th></tr></thead>
                                            <tbody>
                                                <tr >
                                                    <td >validation of successfully deleted</td>
                                                    <td class="text-center bg-success">1</td>
                                                    <td class="text-center ">0</td>
                                                    <td class="text-center ">0</td>
                                                </tr>
                                                <tr >
                                                    <td >Validation of status code 200</td>
                                                    <td class="text-center bg-success">1</td>
                                                    <td class="text-center ">0</td>
                                                    <td class="text-center ">0</td>
                                                </tr>
                                            </tbody>
                                            <tfoot>
                                                <tr class="bg-light">
                                                    <td><strong>Total</strong></td>
                                                    <td class="text-center">2</td>
                                                    <td class="text-center">0</td>
                                                    <td class="text-center">0</td>
                                                </tr>
                                            </tfoot>
                                        </table>
                                    </div>
                                    <div class="row d-none">
                                    <div class="col-sm-12 mb-3">
                                        <div class="card-deck">
                                        <div class="card border-danger" style="width: 50rem;">
                                            <div class="card-body">
                                                <h5 class="card-title text-uppercase text-white text-center bg-danger">Test Failure</h5>
                                                <div class="table-responsive">
                                                    <table class="table table-hover">
                                                    <thead><tr class="text-nowrap"><th>Test Name</th><th>Assertion Error</th></tr></thead>
                                                        <tbody>
                                                        </tbody>
                                                    </table>
                                                </div>
                                            </div>
                                        </div>
                                        </div>
                                    </div>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                    </div>
                </div>
                </div>
            </div>
            </div>
            <div id="folder-a00c9dc5-6cf0-4c8a-9665-52645e4fea72" class="card-deck iteration-1">
            <div class="row iteration-1">
                <div class="col-sm-12 mb-3 iteration-1">
                <div class="card iteration-1">
                    <div class="card-header  bg-success iteration-1">
                        <a data-toggle="collapse" href="#" data-target="#collapse-a00c9dc5-6cf0-4c8a-9665-52645e4fea72" aria-expanded="false" aria-controls="collapse" id="requests-a00c9dc5-6cf0-4c8a-9665-52645e4fea72" class="collapsed text-white z-block">
                    Iteration: 2 - AddBook <i class="float-lg-right fa fa-chevron-down" style="padding-top: 5px;"></i>
                </a>
                    </div>
                    <div id="collapse-a00c9dc5-6cf0-4c8a-9665-52645e4fea72" class="collapse" aria-labelledby="requests-a00c9dc5-6cf0-4c8a-9665-52645e4fea72">
                    <div class="card-body">
                        <div class="row">
                            <div class="col-sm-12 mb-3">
                                <div class="card-deck">
                                <div class="card border-info" style="width: 50rem;">
                                    <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Request Information</h5>
                                    <span><i class="fas fa-info-circle"></i></span><strong> Request Method:</strong> <span class="badge-outline-success badge badge-success"> GET</span><br>
                                    <span><i class="fas fa-info-circle"></i></span><strong> Request URL:</strong> <a href="https://rahulshettyacademy.com/Library/Addbook.php" target="_blank">https://rahulshettyacademy.com/Library/Addbook.php</a><br>
                                    </div>
                                </div>
                                <div class="card border-info" style="width: 50rem;">
                                    <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Response Information</h5>
                                    <span><i class="fas fa-info-circle"></i></span><strong> Response Code:</strong> <span class="float-right badge-outline badge badge-success"> 200 - OK</span><br>
                                    <span><i class="fas fa-stopwatch"></i></span><strong> Mean time per request:</strong> <span class="float-right badge-outline badge badge-success"> 98ms</span><br>
                                    <span><i class="fas fa-database"></i></span><strong> Mean size per request:</strong> <span class="float-right badge-outline badge badge-success"> 44B</span><br>
                                    <hr>
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Test Pass Percentage</h5>
                                    <div>
                                        <div class="progress" style="height: 40px;">
                                            <div class="progress-bar  bg-success" style="width: 100%" role="progressbar">
                                            <h5 style="padding-top:5px;"><strong>100 %</strong></h5>
                                            </div>
                                        </div>
                                    </div>
                                    </div>
                                </div>
                            </div>
                            </div>
                        </div>
                        <div class="row">
                            <div class="col-sm-12 mb-3">
                                <div class="card-deck">
                                <div class="card border-info" style="width: 50rem;">
                                    <div class="card-body">
                                        <h5 class="card-title text-uppercase text-white text-center bg-info">Request Headers</h5>
                                        <div class="table-responsive">
                                            <table class="table table-bordered">
                                            <thead class="thead-light text-center"><tr><th>Header Name</th><th>Header Value</th></tr></thead>
                                                <tbody>
                                                    <tr>
                                                        <td class="text-nowrap">Content-Type</td>
                                                        <td class="text-wrap">application/json</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">User-Agent</td>
                                                        <td class="text-wrap">PostmanRuntime/7.37.1</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Accept</td>
                                                        <td class="text-wrap">*/*</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Cache-Control</td>
                                                        <td class="text-wrap">no-cache</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Postman-Token</td>
                                                        <td class="text-wrap">b1a4b253-b6aa-4b57-b9b3-a3b7234ff93e</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Host</td>
                                                        <td class="text-wrap">rahulshettyacademy.com</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Accept-Encoding</td>
                                                        <td class="text-wrap">gzip, deflate, br</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Connection</td>
                                                        <td class="text-wrap">keep-alive</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Content-Length</td>
                                                        <td class="text-wrap">106</td>
                                                    </tr>
                                                </tbody>
                                            </table>
                                        </div>
                                    </div>
                                </div>
                                </div>
                            </div>
                        </div>
                        <div class="row">
                        <div class="col-sm-12 mb-3">
                            <div class="card-deck">
                            <div class="card border-info" style="width: 50rem;">
                                <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Request Body</h5>
                                        <div class="dyn-height">
                                            <pre><code id="copyReqText-0" class="prettyPrint">{
        
        &quot;name&quot;:&quot;Python for Ethical Hacking&quot;,
        &quot;isbn&quot;:&quot;YC619&quot;,
        &quot;aisle&quot;:&quot;932&quot;,
        &quot;author&quot;:&quot;Rozella Mohr&quot;
        }
        
        </code></pre>
                                        </div>
                                        <div class="card-footer">
                                            <button class="btn btn-outline-secondary btn-sm copyButton" type="button" data-clipboard-action="copy" data-clipboard-target="#copyReqText-0">Copy to Clipboard</button>
                                        </div>
                                </div>
                            </div>
                            </div>
                        </div>
                        </div>
                        <div class="row">
                        <div class="col-sm-12 mb-3">
                            <div class="card-deck">
                            <div class="card border-info" style="width: 50rem;">
                                <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Response Headers</h5>
                                    <div class="table-responsive">
                                        <table class="table table-bordered">
                                        <thead class="thead-light text-center"><tr><th>Header Name</th><th>Header Value</th></tr></thead>
                                            <tbody>
                                                <tr>
                                                    <td class="text-nowrap">Date</td>
                                                    <td class="text-wrap">Mon, 25 Mar 2024 11:05:00 GMT</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Server</td>
                                                    <td class="text-wrap">Apache/2.4.52 (Ubuntu)</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Access-Control-Allow-Origin</td>
                                                    <td class="text-wrap">*</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Access-Control-Allow-Methods</td>
                                                    <td class="text-wrap">POST</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Access-Control-Max-Age</td>
                                                    <td class="text-wrap">3600</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Access-Control-Allow-Headers</td>
                                                    <td class="text-wrap">Content-Type, Access-Control-Allow-Headers, Authorization, X-Requested-With</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Content-Length</td>
                                                    <td class="text-wrap">44</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Keep-Alive</td>
                                                    <td class="text-wrap">timeout&#x3D;5, max&#x3D;96</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Connection</td>
                                                    <td class="text-wrap">Keep-Alive</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Content-Type</td>
                                                    <td class="text-wrap">application/json;charset&#x3D;UTF-8</td>
                                                </tr>
                                            </tbody>
                                        </table>
                                    </div>
                                </div>
                            </div>
                            </div>
                        </div>
                        </div>
                        <div class="row">
                        <div class="col-sm-12 mb-3">
                            <div class="card-deck">
                            <div class="card border-info" style="width: 50rem;">
                                <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Response Body</h5>
                                        <div class="dyn-height">
                                                <pre><code id="copyText-cc6d406a-a829-4cde-b988-3df674dae181" class="prettyPrint">{&quot;Msg&quot;:&quot;successfully added&quot;,&quot;ID&quot;:&quot;YC619932&quot;}</code></pre>
                                        </div>
                                        <div class="card-footer">
                                            <button class="btn btn-outline-secondary btn-sm copyButton" type="button" data-clipboard-action="copy" data-clipboard-target="#copyText-cc6d406a-a829-4cde-b988-3df674dae181">Copy to Clipboard</button>
                                        </div>
                                </div>
                            </div>
                            </div>
                            </div>
                        </div>
                        <div class="row">
                            <div class="card border-info">
                                <div class="card-body">
                                <h5 class="card-title text-uppercase text-white text-center bg-info">Test Information</h5>
                                    <div class="table-responsive text-nowrap">
                                        <table class="datatable table table-hover">
                                        <thead><tr class="text-center"><th>Name</th><th>Passed</th><th>Failed</th><th>Skipped</th></tr></thead>
                                            <tbody>
                                                <tr >
                                                    <td >Validation of status code 200</td>
                                                    <td class="text-center bg-success">1</td>
                                                    <td class="text-center ">0</td>
                                                    <td class="text-center ">0</td>
                                                </tr>
                                                <tr >
                                                    <td >Validation of response jason schema</td>
                                                    <td class="text-center bg-success">1</td>
                                                    <td class="text-center ">0</td>
                                                    <td class="text-center ">0</td>
                                                </tr>
                                                <tr >
                                                    <td >validation of successfully added</td>
                                                    <td class="text-center bg-success">1</td>
                                                    <td class="text-center ">0</td>
                                                    <td class="text-center ">0</td>
                                                </tr>
                                                <tr >
                                                    <td >Validation of Respose time below 1600</td>
                                                    <td class="text-center bg-success">1</td>
                                                    <td class="text-center ">0</td>
                                                    <td class="text-center ">0</td>
                                                </tr>
                                            </tbody>
                                            <tfoot>
                                                <tr class="bg-light">
                                                    <td><strong>Total</strong></td>
                                                    <td class="text-center">4</td>
                                                    <td class="text-center">0</td>
                                                    <td class="text-center">0</td>
                                                </tr>
                                            </tfoot>
                                        </table>
                                    </div>
                                    <div class="row d-none">
                                    <div class="col-sm-12 mb-3">
                                        <div class="card-deck">
                                        <div class="card border-danger" style="width: 50rem;">
                                            <div class="card-body">
                                                <h5 class="card-title text-uppercase text-white text-center bg-danger">Test Failure</h5>
                                                <div class="table-responsive">
                                                    <table class="table table-hover">
                                                    <thead><tr class="text-nowrap"><th>Test Name</th><th>Assertion Error</th></tr></thead>
                                                        <tbody>
                                                        </tbody>
                                                    </table>
                                                </div>
                                            </div>
                                        </div>
                                        </div>
                                    </div>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                    </div>
                </div>
                </div>
            </div>
            </div>
            <div id="folder-3b722c97-19c8-4e4f-a755-13b24a54bc64" class="card-deck iteration-1">
            <div class="row iteration-1">
                <div class="col-sm-12 mb-3 iteration-1">
                <div class="card iteration-1">
                    <div class="card-header  bg-success iteration-1">
                        <a data-toggle="collapse" href="#" data-target="#collapse-3b722c97-19c8-4e4f-a755-13b24a54bc64" aria-expanded="false" aria-controls="collapse" id="requests-3b722c97-19c8-4e4f-a755-13b24a54bc64" class="collapsed text-white z-block">
                    Iteration: 2 - GetBookByID <i class="float-lg-right fa fa-chevron-down" style="padding-top: 5px;"></i>
                </a>
                    </div>
                    <div id="collapse-3b722c97-19c8-4e4f-a755-13b24a54bc64" class="collapse" aria-labelledby="requests-3b722c97-19c8-4e4f-a755-13b24a54bc64">
                    <div class="card-body">
                        <div class="row">
                            <div class="col-sm-12 mb-3">
                                <div class="card-deck">
                                <div class="card border-info" style="width: 50rem;">
                                    <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Request Information</h5>
                                    <span><i class="fas fa-info-circle"></i></span><strong> Request Method:</strong> <span class="badge-outline-success badge badge-success"> GET</span><br>
                                    <span><i class="fas fa-info-circle"></i></span><strong> Request URL:</strong> <a href="https://rahulshettyacademy.com/Library/GetBook.php?ID&#x3D;YC619932" target="_blank">https://rahulshettyacademy.com/Library/GetBook.php?ID&#x3D;YC619932</a><br>
                                    </div>
                                </div>
                                <div class="card border-info" style="width: 50rem;">
                                    <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Response Information</h5>
                                    <span><i class="fas fa-info-circle"></i></span><strong> Response Code:</strong> <span class="float-right badge-outline badge badge-success"> 200 - OK</span><br>
                                    <span><i class="fas fa-stopwatch"></i></span><strong> Mean time per request:</strong> <span class="float-right badge-outline badge badge-success"> 94ms</span><br>
                                    <span><i class="fas fa-database"></i></span><strong> Mean size per request:</strong> <span class="float-right badge-outline badge badge-success"> 97B</span><br>
                                    <hr>
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Test Pass Percentage</h5>
                                    <div>
                                        <div class="progress" style="height: 40px;">
                                            <div class="progress-bar  bg-success" style="width: 100%" role="progressbar">
                                            <h5 style="padding-top:5px;"><strong>100 %</strong></h5>
                                            </div>
                                        </div>
                                    </div>
                                    </div>
                                </div>
                            </div>
                            </div>
                        </div>
                        <div class="row">
                            <div class="col-sm-12 mb-3">
                                <div class="card-deck">
                                <div class="card border-info" style="width: 50rem;">
                                    <div class="card-body">
                                        <h5 class="card-title text-uppercase text-white text-center bg-info">Request Headers</h5>
                                        <div class="table-responsive">
                                            <table class="table table-bordered">
                                            <thead class="thead-light text-center"><tr><th>Header Name</th><th>Header Value</th></tr></thead>
                                                <tbody>
                                                    <tr>
                                                        <td class="text-nowrap">User-Agent</td>
                                                        <td class="text-wrap">PostmanRuntime/7.37.1</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Accept</td>
                                                        <td class="text-wrap">*/*</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Cache-Control</td>
                                                        <td class="text-wrap">no-cache</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Postman-Token</td>
                                                        <td class="text-wrap">876174d3-45ad-4d21-9a83-e7c820855202</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Host</td>
                                                        <td class="text-wrap">rahulshettyacademy.com</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Accept-Encoding</td>
                                                        <td class="text-wrap">gzip, deflate, br</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Connection</td>
                                                        <td class="text-wrap">keep-alive</td>
                                                    </tr>
                                                </tbody>
                                            </table>
                                        </div>
                                    </div>
                                </div>
                                </div>
                            </div>
                        </div>
                        <div class="row">
                        <div class="col-sm-12 mb-3">
                            <div class="card-deck">
                            <div class="card border-info" style="width: 50rem;">
                                <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Response Headers</h5>
                                    <div class="table-responsive">
                                        <table class="table table-bordered">
                                        <thead class="thead-light text-center"><tr><th>Header Name</th><th>Header Value</th></tr></thead>
                                            <tbody>
                                                <tr>
                                                    <td class="text-nowrap">Date</td>
                                                    <td class="text-wrap">Mon, 25 Mar 2024 11:05:01 GMT</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Server</td>
                                                    <td class="text-wrap">Apache/2.4.52 (Ubuntu)</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Access-Control-Allow-Origin</td>
                                                    <td class="text-wrap">*</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Access-Control-Allow-Methods</td>
                                                    <td class="text-wrap">POST</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Access-Control-Max-Age</td>
                                                    <td class="text-wrap">3600</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Access-Control-Allow-Headers</td>
                                                    <td class="text-wrap">Content-Type, Access-Control-Allow-Headers, Authorization, X-Requested-With</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Content-Length</td>
                                                    <td class="text-wrap">97</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Keep-Alive</td>
                                                    <td class="text-wrap">timeout&#x3D;5, max&#x3D;95</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Connection</td>
                                                    <td class="text-wrap">Keep-Alive</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Content-Type</td>
                                                    <td class="text-wrap">application/json;charset&#x3D;UTF-8</td>
                                                </tr>
                                            </tbody>
                                        </table>
                                    </div>
                                </div>
                            </div>
                            </div>
                        </div>
                        </div>
                        <div class="row">
                        <div class="col-sm-12 mb-3">
                            <div class="card-deck">
                            <div class="card border-info" style="width: 50rem;">
                                <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Response Body</h5>
                                        <div class="dyn-height">
                                                <pre><code id="copyText-909a8cbf-6e67-4645-87b1-f46ac9717948" class="prettyPrint">[{&quot;book_name&quot;:&quot;Python for Ethical Hacking&quot;,&quot;isbn&quot;:&quot;YC619&quot;,&quot;aisle&quot;:&quot;932&quot;,&quot;author&quot;:&quot;Rozella Mohr&quot;}]</code></pre>
                                        </div>
                                        <div class="card-footer">
                                            <button class="btn btn-outline-secondary btn-sm copyButton" type="button" data-clipboard-action="copy" data-clipboard-target="#copyText-909a8cbf-6e67-4645-87b1-f46ac9717948">Copy to Clipboard</button>
                                        </div>
                                </div>
                            </div>
                            </div>
                            </div>
                        </div>
                        <div class="row">
                            <div class="card border-info">
                                <div class="card-body">
                                <h5 class="card-title text-uppercase text-white text-center bg-info">Test Information</h5>
                                    <div class="table-responsive text-nowrap">
                                        <table class="datatable table table-hover">
                                        <thead><tr class="text-center"><th>Name</th><th>Passed</th><th>Failed</th><th>Skipped</th></tr></thead>
                                            <tbody>
                                                <tr >
                                                    <td >Validation of status code 200</td>
                                                    <td class="text-center bg-success">1</td>
                                                    <td class="text-center ">0</td>
                                                    <td class="text-center ">0</td>
                                                </tr>
                                                <tr >
                                                    <td >Validation of response jason schema</td>
                                                    <td class="text-center bg-success">1</td>
                                                    <td class="text-center ">0</td>
                                                    <td class="text-center ">0</td>
                                                </tr>
                                                <tr >
                                                    <td >validation of  aisle and Author name </td>
                                                    <td class="text-center bg-success">1</td>
                                                    <td class="text-center ">0</td>
                                                    <td class="text-center ">0</td>
                                                </tr>
                                            </tbody>
                                            <tfoot>
                                                <tr class="bg-light">
                                                    <td><strong>Total</strong></td>
                                                    <td class="text-center">3</td>
                                                    <td class="text-center">0</td>
                                                    <td class="text-center">0</td>
                                                </tr>
                                            </tfoot>
                                        </table>
                                    </div>
                                    <div class="row d-none">
                                    <div class="col-sm-12 mb-3">
                                        <div class="card-deck">
                                        <div class="card border-danger" style="width: 50rem;">
                                            <div class="card-body">
                                                <h5 class="card-title text-uppercase text-white text-center bg-danger">Test Failure</h5>
                                                <div class="table-responsive">
                                                    <table class="table table-hover">
                                                    <thead><tr class="text-nowrap"><th>Test Name</th><th>Assertion Error</th></tr></thead>
                                                        <tbody>
                                                        </tbody>
                                                    </table>
                                                </div>
                                            </div>
                                        </div>
                                        </div>
                                    </div>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                    </div>
                </div>
                </div>
            </div>
            </div>
            <div id="folder-aed24b74-a9e3-49bf-a498-ca699eb4ece5" class="card-deck iteration-1">
            <div class="row iteration-1">
                <div class="col-sm-12 mb-3 iteration-1">
                <div class="card iteration-1">
                    <div class="card-header  bg-success iteration-1">
                        <a data-toggle="collapse" href="#" data-target="#collapse-aed24b74-a9e3-49bf-a498-ca699eb4ece5" aria-expanded="false" aria-controls="collapse" id="requests-aed24b74-a9e3-49bf-a498-ca699eb4ece5" class="collapsed text-white z-block">
                    Iteration: 2 - GetBookByAuthor <i class="float-lg-right fa fa-chevron-down" style="padding-top: 5px;"></i>
                </a>
                    </div>
                    <div id="collapse-aed24b74-a9e3-49bf-a498-ca699eb4ece5" class="collapse" aria-labelledby="requests-aed24b74-a9e3-49bf-a498-ca699eb4ece5">
                    <div class="card-body">
                        <div class="row">
                            <div class="col-sm-12 mb-3">
                                <div class="card-deck">
                                <div class="card border-info" style="width: 50rem;">
                                    <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Request Information</h5>
                                    <span><i class="fas fa-info-circle"></i></span><strong> Request Method:</strong> <span class="badge-outline-success badge badge-success"> GET</span><br>
                                    <span><i class="fas fa-info-circle"></i></span><strong> Request URL:</strong> <a href="https://rahulshettyacademy.com/Library/GetBook.php?AuthorName&#x3D;Rozella%20Mohr" target="_blank">https://rahulshettyacademy.com/Library/GetBook.php?AuthorName&#x3D;Rozella%20Mohr</a><br>
                                    </div>
                                </div>
                                <div class="card border-info" style="width: 50rem;">
                                    <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Response Information</h5>
                                    <span><i class="fas fa-info-circle"></i></span><strong> Response Code:</strong> <span class="float-right badge-outline badge badge-success"> 200 - OK</span><br>
                                    <span><i class="fas fa-stopwatch"></i></span><strong> Mean time per request:</strong> <span class="float-right badge-outline badge badge-success"> 140ms</span><br>
                                    <span><i class="fas fa-database"></i></span><strong> Mean size per request:</strong> <span class="float-right badge-outline badge badge-success"> 73B</span><br>
                                    <hr>
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Test Pass Percentage</h5>
                                    <div>
                                        <div class="progress" style="height: 40px;">
                                            <div class="progress-bar bg-success" style="width: 100%" role="progressbar">
                                            <h5 class="text-uppercase text-white text-center" style="padding-top:5px;"><strong>No Tests for this request</strong></h5>
                                            </div>
                                        </div>
                                    </div>
                                    </div>
                                </div>
                            </div>
                            </div>
                        </div>
                        <div class="row">
                            <div class="col-sm-12 mb-3">
                                <div class="card-deck">
                                <div class="card border-info" style="width: 50rem;">
                                    <div class="card-body">
                                        <h5 class="card-title text-uppercase text-white text-center bg-info">Request Headers</h5>
                                        <div class="table-responsive">
                                            <table class="table table-bordered">
                                            <thead class="thead-light text-center"><tr><th>Header Name</th><th>Header Value</th></tr></thead>
                                                <tbody>
                                                    <tr>
                                                        <td class="text-nowrap">User-Agent</td>
                                                        <td class="text-wrap">PostmanRuntime/7.37.1</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Accept</td>
                                                        <td class="text-wrap">*/*</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Cache-Control</td>
                                                        <td class="text-wrap">no-cache</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Postman-Token</td>
                                                        <td class="text-wrap">f95f002b-ee59-48e2-85f6-c5c762fb2f7b</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Host</td>
                                                        <td class="text-wrap">rahulshettyacademy.com</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Accept-Encoding</td>
                                                        <td class="text-wrap">gzip, deflate, br</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Connection</td>
                                                        <td class="text-wrap">keep-alive</td>
                                                    </tr>
                                                </tbody>
                                            </table>
                                        </div>
                                    </div>
                                </div>
                                </div>
                            </div>
                        </div>
                        <div class="row">
                        <div class="col-sm-12 mb-3">
                            <div class="card-deck">
                            <div class="card border-info" style="width: 50rem;">
                                <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Response Headers</h5>
                                    <div class="table-responsive">
                                        <table class="table table-bordered">
                                        <thead class="thead-light text-center"><tr><th>Header Name</th><th>Header Value</th></tr></thead>
                                            <tbody>
                                                <tr>
                                                    <td class="text-nowrap">Date</td>
                                                    <td class="text-wrap">Mon, 25 Mar 2024 11:05:01 GMT</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Server</td>
                                                    <td class="text-wrap">Apache/2.4.52 (Ubuntu)</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Access-Control-Allow-Origin</td>
                                                    <td class="text-wrap">*</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Access-Control-Allow-Methods</td>
                                                    <td class="text-wrap">POST</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Access-Control-Max-Age</td>
                                                    <td class="text-wrap">3600</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Access-Control-Allow-Headers</td>
                                                    <td class="text-wrap">Content-Type, Access-Control-Allow-Headers, Authorization, X-Requested-With</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Content-Length</td>
                                                    <td class="text-wrap">73</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Keep-Alive</td>
                                                    <td class="text-wrap">timeout&#x3D;5, max&#x3D;94</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Connection</td>
                                                    <td class="text-wrap">Keep-Alive</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Content-Type</td>
                                                    <td class="text-wrap">application/json;charset&#x3D;UTF-8</td>
                                                </tr>
                                            </tbody>
                                        </table>
                                    </div>
                                </div>
                            </div>
                            </div>
                        </div>
                        </div>
                        <div class="row">
                        <div class="col-sm-12 mb-3">
                            <div class="card-deck">
                            <div class="card border-info" style="width: 50rem;">
                                <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Response Body</h5>
                                        <div class="dyn-height">
                                                <pre><code id="copyText-ac5ed8e1-a353-4a87-96f4-eed7aa1a66d6" class="prettyPrint">[{&quot;book_name&quot;:&quot;Python for Ethical Hacking&quot;,&quot;isbn&quot;:&quot;YC619&quot;,&quot;aisle&quot;:&quot;932&quot;}]</code></pre>
                                        </div>
                                        <div class="card-footer">
                                            <button class="btn btn-outline-secondary btn-sm copyButton" type="button" data-clipboard-action="copy" data-clipboard-target="#copyText-ac5ed8e1-a353-4a87-96f4-eed7aa1a66d6">Copy to Clipboard</button>
                                        </div>
                                </div>
                            </div>
                            </div>
                            </div>
                        </div>
                        <div class="row">
                            <div class="card border-info">
                                <div class="card-body">
                                <h5 class="card-title text-uppercase text-white text-center bg-info">Test Information</h5>
                                    <h5 class="alert alert-success text-uppercase text-center">No Tests for this request</h5>
                                </div>
                            </div>
                        </div>
                    </div>
                    </div>
                </div>
                </div>
            </div>
            </div>
            <div id="folder-70002bef-fd90-4087-9fe7-3f2c8fb58c17" class="card-deck iteration-1">
            <div class="row iteration-1">
                <div class="col-sm-12 mb-3 iteration-1">
                <div class="card iteration-1">
                    <div class="card-header  bg-success iteration-1">
                        <a data-toggle="collapse" href="#" data-target="#collapse-70002bef-fd90-4087-9fe7-3f2c8fb58c17" aria-expanded="false" aria-controls="collapse" id="requests-70002bef-fd90-4087-9fe7-3f2c8fb58c17" class="collapsed text-white z-block">
                    Iteration: 2 - DeleteBookByID <i class="float-lg-right fa fa-chevron-down" style="padding-top: 5px;"></i>
                </a>
                    </div>
                    <div id="collapse-70002bef-fd90-4087-9fe7-3f2c8fb58c17" class="collapse" aria-labelledby="requests-70002bef-fd90-4087-9fe7-3f2c8fb58c17">
                    <div class="card-body">
                        <div class="row">
                            <div class="col-sm-12 mb-3">
                                <div class="card-deck">
                                <div class="card border-info" style="width: 50rem;">
                                    <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Request Information</h5>
                                    <span><i class="fas fa-info-circle"></i></span><strong> Request Method:</strong> <span class="badge-outline-success badge badge-success"> POST</span><br>
                                    <span><i class="fas fa-info-circle"></i></span><strong> Request URL:</strong> <a href="https://rahulshettyacademy.com/Library/DeleteBook.php" target="_blank">https://rahulshettyacademy.com/Library/DeleteBook.php</a><br>
                                    </div>
                                </div>
                                <div class="card border-info" style="width: 50rem;">
                                    <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Response Information</h5>
                                    <span><i class="fas fa-info-circle"></i></span><strong> Response Code:</strong> <span class="float-right badge-outline badge badge-success"> 200 - OK</span><br>
                                    <span><i class="fas fa-stopwatch"></i></span><strong> Mean time per request:</strong> <span class="float-right badge-outline badge badge-success"> 99ms</span><br>
                                    <span><i class="fas fa-database"></i></span><strong> Mean size per request:</strong> <span class="float-right badge-outline badge badge-success"> 38B</span><br>
                                    <hr>
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Test Pass Percentage</h5>
                                    <div>
                                        <div class="progress" style="height: 40px;">
                                            <div class="progress-bar  bg-success" style="width: 100%" role="progressbar">
                                            <h5 style="padding-top:5px;"><strong>100 %</strong></h5>
                                            </div>
                                        </div>
                                    </div>
                                    </div>
                                </div>
                            </div>
                            </div>
                        </div>
                        <div class="row">
                            <div class="col-sm-12 mb-3">
                                <div class="card-deck">
                                <div class="card border-info" style="width: 50rem;">
                                    <div class="card-body">
                                        <h5 class="card-title text-uppercase text-white text-center bg-info">Request Headers</h5>
                                        <div class="table-responsive">
                                            <table class="table table-bordered">
                                            <thead class="thead-light text-center"><tr><th>Header Name</th><th>Header Value</th></tr></thead>
                                                <tbody>
                                                    <tr>
                                                        <td class="text-nowrap">Content-Type</td>
                                                        <td class="text-wrap">application/json</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">User-Agent</td>
                                                        <td class="text-wrap">PostmanRuntime/7.37.1</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Accept</td>
                                                        <td class="text-wrap">*/*</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Cache-Control</td>
                                                        <td class="text-wrap">no-cache</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Postman-Token</td>
                                                        <td class="text-wrap">25aa83bb-fe7d-4367-a875-7f085f0cdc09</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Host</td>
                                                        <td class="text-wrap">rahulshettyacademy.com</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Accept-Encoding</td>
                                                        <td class="text-wrap">gzip, deflate, br</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Connection</td>
                                                        <td class="text-wrap">keep-alive</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Content-Length</td>
                                                        <td class="text-wrap">30</td>
                                                    </tr>
                                                </tbody>
                                            </table>
                                        </div>
                                    </div>
                                </div>
                                </div>
                            </div>
                        </div>
                        <div class="row">
                        <div class="col-sm-12 mb-3">
                            <div class="card-deck">
                            <div class="card border-info" style="width: 50rem;">
                                <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Request Body</h5>
                                        <div class="dyn-height">
                                            <pre><code id="copyReqText-3" class="prettyPrint">{
        
        &quot;ID&quot; : &quot;YC619932&quot;
         
        }
        </code></pre>
                                        </div>
                                        <div class="card-footer">
                                            <button class="btn btn-outline-secondary btn-sm copyButton" type="button" data-clipboard-action="copy" data-clipboard-target="#copyReqText-3">Copy to Clipboard</button>
                                        </div>
                                </div>
                            </div>
                            </div>
                        </div>
                        </div>
                        <div class="row">
                        <div class="col-sm-12 mb-3">
                            <div class="card-deck">
                            <div class="card border-info" style="width: 50rem;">
                                <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Response Headers</h5>
                                    <div class="table-responsive">
                                        <table class="table table-bordered">
                                        <thead class="thead-light text-center"><tr><th>Header Name</th><th>Header Value</th></tr></thead>
                                            <tbody>
                                                <tr>
                                                    <td class="text-nowrap">Date</td>
                                                    <td class="text-wrap">Mon, 25 Mar 2024 11:05:01 GMT</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Server</td>
                                                    <td class="text-wrap">Apache/2.4.52 (Ubuntu)</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Access-Control-Allow-Origin</td>
                                                    <td class="text-wrap">*</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Access-Control-Allow-Methods</td>
                                                    <td class="text-wrap">POST</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Access-Control-Max-Age</td>
                                                    <td class="text-wrap">3600</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Access-Control-Allow-Headers</td>
                                                    <td class="text-wrap">Content-Type, Access-Control-Allow-Headers, Authorization, X-Requested-With</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Content-Length</td>
                                                    <td class="text-wrap">38</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Keep-Alive</td>
                                                    <td class="text-wrap">timeout&#x3D;5, max&#x3D;93</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Connection</td>
                                                    <td class="text-wrap">Keep-Alive</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Content-Type</td>
                                                    <td class="text-wrap">application/json;charset&#x3D;UTF-8</td>
                                                </tr>
                                            </tbody>
                                        </table>
                                    </div>
                                </div>
                            </div>
                            </div>
                        </div>
                        </div>
                        <div class="row">
                        <div class="col-sm-12 mb-3">
                            <div class="card-deck">
                            <div class="card border-info" style="width: 50rem;">
                                <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Response Body</h5>
                                        <div class="dyn-height">
                                                <pre><code id="copyText-30e9c746-68d6-477c-b5b4-e99c496819dc" class="prettyPrint">{&quot;msg&quot;:&quot;book is successfully deleted&quot;}</code></pre>
                                        </div>
                                        <div class="card-footer">
                                            <button class="btn btn-outline-secondary btn-sm copyButton" type="button" data-clipboard-action="copy" data-clipboard-target="#copyText-30e9c746-68d6-477c-b5b4-e99c496819dc">Copy to Clipboard</button>
                                        </div>
                                </div>
                            </div>
                            </div>
                            </div>
                        </div>
                        <div class="row">
                            <div class="card border-info">
                                <div class="card-body">
                                <h5 class="card-title text-uppercase text-white text-center bg-info">Test Information</h5>
                                    <div class="table-responsive text-nowrap">
                                        <table class="datatable table table-hover">
                                        <thead><tr class="text-center"><th>Name</th><th>Passed</th><th>Failed</th><th>Skipped</th></tr></thead>
                                            <tbody>
                                                <tr >
                                                    <td >validation of successfully deleted</td>
                                                    <td class="text-center bg-success">1</td>
                                                    <td class="text-center ">0</td>
                                                    <td class="text-center ">0</td>
                                                </tr>
                                                <tr >
                                                    <td >Validation of status code 200</td>
                                                    <td class="text-center bg-success">1</td>
                                                    <td class="text-center ">0</td>
                                                    <td class="text-center ">0</td>
                                                </tr>
                                            </tbody>
                                            <tfoot>
                                                <tr class="bg-light">
                                                    <td><strong>Total</strong></td>
                                                    <td class="text-center">2</td>
                                                    <td class="text-center">0</td>
                                                    <td class="text-center">0</td>
                                                </tr>
                                            </tfoot>
                                        </table>
                                    </div>
                                    <div class="row d-none">
                                    <div class="col-sm-12 mb-3">
                                        <div class="card-deck">
                                        <div class="card border-danger" style="width: 50rem;">
                                            <div class="card-body">
                                                <h5 class="card-title text-uppercase text-white text-center bg-danger">Test Failure</h5>
                                                <div class="table-responsive">
                                                    <table class="table table-hover">
                                                    <thead><tr class="text-nowrap"><th>Test Name</th><th>Assertion Error</th></tr></thead>
                                                        <tbody>
                                                        </tbody>
                                                    </table>
                                                </div>
                                            </div>
                                        </div>
                                        </div>
                                    </div>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                    </div>
                </div>
                </div>
            </div>
            </div>
            <div id="folder-06834e6a-2d58-44fd-a9b2-e1fe81325499" class="card-deck iteration-2">
            <div class="row iteration-2">
                <div class="col-sm-12 mb-3 iteration-2">
                <div class="card iteration-2">
                    <div class="card-header  bg-success iteration-2">
                        <a data-toggle="collapse" href="#" data-target="#collapse-06834e6a-2d58-44fd-a9b2-e1fe81325499" aria-expanded="false" aria-controls="collapse" id="requests-06834e6a-2d58-44fd-a9b2-e1fe81325499" class="collapsed text-white z-block">
                    Iteration: 3 - AddBook <i class="float-lg-right fa fa-chevron-down" style="padding-top: 5px;"></i>
                </a>
                    </div>
                    <div id="collapse-06834e6a-2d58-44fd-a9b2-e1fe81325499" class="collapse" aria-labelledby="requests-06834e6a-2d58-44fd-a9b2-e1fe81325499">
                    <div class="card-body">
                        <div class="row">
                            <div class="col-sm-12 mb-3">
                                <div class="card-deck">
                                <div class="card border-info" style="width: 50rem;">
                                    <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Request Information</h5>
                                    <span><i class="fas fa-info-circle"></i></span><strong> Request Method:</strong> <span class="badge-outline-success badge badge-success"> GET</span><br>
                                    <span><i class="fas fa-info-circle"></i></span><strong> Request URL:</strong> <a href="https://rahulshettyacademy.com/Library/Addbook.php" target="_blank">https://rahulshettyacademy.com/Library/Addbook.php</a><br>
                                    </div>
                                </div>
                                <div class="card border-info" style="width: 50rem;">
                                    <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Response Information</h5>
                                    <span><i class="fas fa-info-circle"></i></span><strong> Response Code:</strong> <span class="float-right badge-outline badge badge-success"> 200 - OK</span><br>
                                    <span><i class="fas fa-stopwatch"></i></span><strong> Mean time per request:</strong> <span class="float-right badge-outline badge badge-success"> 99ms</span><br>
                                    <span><i class="fas fa-database"></i></span><strong> Mean size per request:</strong> <span class="float-right badge-outline badge badge-success"> 44B</span><br>
                                    <hr>
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Test Pass Percentage</h5>
                                    <div>
                                        <div class="progress" style="height: 40px;">
                                            <div class="progress-bar  bg-success" style="width: 100%" role="progressbar">
                                            <h5 style="padding-top:5px;"><strong>100 %</strong></h5>
                                            </div>
                                        </div>
                                    </div>
                                    </div>
                                </div>
                            </div>
                            </div>
                        </div>
                        <div class="row">
                            <div class="col-sm-12 mb-3">
                                <div class="card-deck">
                                <div class="card border-info" style="width: 50rem;">
                                    <div class="card-body">
                                        <h5 class="card-title text-uppercase text-white text-center bg-info">Request Headers</h5>
                                        <div class="table-responsive">
                                            <table class="table table-bordered">
                                            <thead class="thead-light text-center"><tr><th>Header Name</th><th>Header Value</th></tr></thead>
                                                <tbody>
                                                    <tr>
                                                        <td class="text-nowrap">Content-Type</td>
                                                        <td class="text-wrap">application/json</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">User-Agent</td>
                                                        <td class="text-wrap">PostmanRuntime/7.37.1</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Accept</td>
                                                        <td class="text-wrap">*/*</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Cache-Control</td>
                                                        <td class="text-wrap">no-cache</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Postman-Token</td>
                                                        <td class="text-wrap">12109a74-af6e-44a8-b793-025093431ebe</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Host</td>
                                                        <td class="text-wrap">rahulshettyacademy.com</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Accept-Encoding</td>
                                                        <td class="text-wrap">gzip, deflate, br</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Connection</td>
                                                        <td class="text-wrap">keep-alive</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Content-Length</td>
                                                        <td class="text-wrap">108</td>
                                                    </tr>
                                                </tbody>
                                            </table>
                                        </div>
                                    </div>
                                </div>
                                </div>
                            </div>
                        </div>
                        <div class="row">
                        <div class="col-sm-12 mb-3">
                            <div class="card-deck">
                            <div class="card border-info" style="width: 50rem;">
                                <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Request Body</h5>
                                        <div class="dyn-height">
                                            <pre><code id="copyReqText-0" class="prettyPrint">{
        
        &quot;name&quot;:&quot;Python for Ethical Hacking&quot;,
        &quot;isbn&quot;:&quot;YC471&quot;,
        &quot;aisle&quot;:&quot;296&quot;,
        &quot;author&quot;:&quot;Maximo Fritsch&quot;
        }
        
        </code></pre>
                                        </div>
                                        <div class="card-footer">
                                            <button class="btn btn-outline-secondary btn-sm copyButton" type="button" data-clipboard-action="copy" data-clipboard-target="#copyReqText-0">Copy to Clipboard</button>
                                        </div>
                                </div>
                            </div>
                            </div>
                        </div>
                        </div>
                        <div class="row">
                        <div class="col-sm-12 mb-3">
                            <div class="card-deck">
                            <div class="card border-info" style="width: 50rem;">
                                <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Response Headers</h5>
                                    <div class="table-responsive">
                                        <table class="table table-bordered">
                                        <thead class="thead-light text-center"><tr><th>Header Name</th><th>Header Value</th></tr></thead>
                                            <tbody>
                                                <tr>
                                                    <td class="text-nowrap">Date</td>
                                                    <td class="text-wrap">Mon, 25 Mar 2024 11:05:01 GMT</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Server</td>
                                                    <td class="text-wrap">Apache/2.4.52 (Ubuntu)</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Access-Control-Allow-Origin</td>
                                                    <td class="text-wrap">*</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Access-Control-Allow-Methods</td>
                                                    <td class="text-wrap">POST</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Access-Control-Max-Age</td>
                                                    <td class="text-wrap">3600</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Access-Control-Allow-Headers</td>
                                                    <td class="text-wrap">Content-Type, Access-Control-Allow-Headers, Authorization, X-Requested-With</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Content-Length</td>
                                                    <td class="text-wrap">44</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Keep-Alive</td>
                                                    <td class="text-wrap">timeout&#x3D;5, max&#x3D;92</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Connection</td>
                                                    <td class="text-wrap">Keep-Alive</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Content-Type</td>
                                                    <td class="text-wrap">application/json;charset&#x3D;UTF-8</td>
                                                </tr>
                                            </tbody>
                                        </table>
                                    </div>
                                </div>
                            </div>
                            </div>
                        </div>
                        </div>
                        <div class="row">
                        <div class="col-sm-12 mb-3">
                            <div class="card-deck">
                            <div class="card border-info" style="width: 50rem;">
                                <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Response Body</h5>
                                        <div class="dyn-height">
                                                <pre><code id="copyText-cc6d406a-a829-4cde-b988-3df674dae181" class="prettyPrint">{&quot;Msg&quot;:&quot;successfully added&quot;,&quot;ID&quot;:&quot;YC471296&quot;}</code></pre>
                                        </div>
                                        <div class="card-footer">
                                            <button class="btn btn-outline-secondary btn-sm copyButton" type="button" data-clipboard-action="copy" data-clipboard-target="#copyText-cc6d406a-a829-4cde-b988-3df674dae181">Copy to Clipboard</button>
                                        </div>
                                </div>
                            </div>
                            </div>
                            </div>
                        </div>
                        <div class="row">
                            <div class="card border-info">
                                <div class="card-body">
                                <h5 class="card-title text-uppercase text-white text-center bg-info">Test Information</h5>
                                    <div class="table-responsive text-nowrap">
                                        <table class="datatable table table-hover">
                                        <thead><tr class="text-center"><th>Name</th><th>Passed</th><th>Failed</th><th>Skipped</th></tr></thead>
                                            <tbody>
                                                <tr >
                                                    <td >Validation of status code 200</td>
                                                    <td class="text-center bg-success">1</td>
                                                    <td class="text-center ">0</td>
                                                    <td class="text-center ">0</td>
                                                </tr>
                                                <tr >
                                                    <td >Validation of response jason schema</td>
                                                    <td class="text-center bg-success">1</td>
                                                    <td class="text-center ">0</td>
                                                    <td class="text-center ">0</td>
                                                </tr>
                                                <tr >
                                                    <td >validation of successfully added</td>
                                                    <td class="text-center bg-success">1</td>
                                                    <td class="text-center ">0</td>
                                                    <td class="text-center ">0</td>
                                                </tr>
                                                <tr >
                                                    <td >Validation of Respose time below 1600</td>
                                                    <td class="text-center bg-success">1</td>
                                                    <td class="text-center ">0</td>
                                                    <td class="text-center ">0</td>
                                                </tr>
                                            </tbody>
                                            <tfoot>
                                                <tr class="bg-light">
                                                    <td><strong>Total</strong></td>
                                                    <td class="text-center">4</td>
                                                    <td class="text-center">0</td>
                                                    <td class="text-center">0</td>
                                                </tr>
                                            </tfoot>
                                        </table>
                                    </div>
                                    <div class="row d-none">
                                    <div class="col-sm-12 mb-3">
                                        <div class="card-deck">
                                        <div class="card border-danger" style="width: 50rem;">
                                            <div class="card-body">
                                                <h5 class="card-title text-uppercase text-white text-center bg-danger">Test Failure</h5>
                                                <div class="table-responsive">
                                                    <table class="table table-hover">
                                                    <thead><tr class="text-nowrap"><th>Test Name</th><th>Assertion Error</th></tr></thead>
                                                        <tbody>
                                                        </tbody>
                                                    </table>
                                                </div>
                                            </div>
                                        </div>
                                        </div>
                                    </div>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                    </div>
                </div>
                </div>
            </div>
            </div>
            <div id="folder-c8d8247c-a1f3-4979-a236-cafd9f24c702" class="card-deck iteration-2">
            <div class="row iteration-2">
                <div class="col-sm-12 mb-3 iteration-2">
                <div class="card iteration-2">
                    <div class="card-header  bg-success iteration-2">
                        <a data-toggle="collapse" href="#" data-target="#collapse-c8d8247c-a1f3-4979-a236-cafd9f24c702" aria-expanded="false" aria-controls="collapse" id="requests-c8d8247c-a1f3-4979-a236-cafd9f24c702" class="collapsed text-white z-block">
                    Iteration: 3 - GetBookByID <i class="float-lg-right fa fa-chevron-down" style="padding-top: 5px;"></i>
                </a>
                    </div>
                    <div id="collapse-c8d8247c-a1f3-4979-a236-cafd9f24c702" class="collapse" aria-labelledby="requests-c8d8247c-a1f3-4979-a236-cafd9f24c702">
                    <div class="card-body">
                        <div class="row">
                            <div class="col-sm-12 mb-3">
                                <div class="card-deck">
                                <div class="card border-info" style="width: 50rem;">
                                    <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Request Information</h5>
                                    <span><i class="fas fa-info-circle"></i></span><strong> Request Method:</strong> <span class="badge-outline-success badge badge-success"> GET</span><br>
                                    <span><i class="fas fa-info-circle"></i></span><strong> Request URL:</strong> <a href="https://rahulshettyacademy.com/Library/GetBook.php?ID&#x3D;YC471296" target="_blank">https://rahulshettyacademy.com/Library/GetBook.php?ID&#x3D;YC471296</a><br>
                                    </div>
                                </div>
                                <div class="card border-info" style="width: 50rem;">
                                    <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Response Information</h5>
                                    <span><i class="fas fa-info-circle"></i></span><strong> Response Code:</strong> <span class="float-right badge-outline badge badge-success"> 200 - OK</span><br>
                                    <span><i class="fas fa-stopwatch"></i></span><strong> Mean time per request:</strong> <span class="float-right badge-outline badge badge-success"> 91ms</span><br>
                                    <span><i class="fas fa-database"></i></span><strong> Mean size per request:</strong> <span class="float-right badge-outline badge badge-success"> 99B</span><br>
                                    <hr>
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Test Pass Percentage</h5>
                                    <div>
                                        <div class="progress" style="height: 40px;">
                                            <div class="progress-bar  bg-success" style="width: 100%" role="progressbar">
                                            <h5 style="padding-top:5px;"><strong>100 %</strong></h5>
                                            </div>
                                        </div>
                                    </div>
                                    </div>
                                </div>
                            </div>
                            </div>
                        </div>
                        <div class="row">
                            <div class="col-sm-12 mb-3">
                                <div class="card-deck">
                                <div class="card border-info" style="width: 50rem;">
                                    <div class="card-body">
                                        <h5 class="card-title text-uppercase text-white text-center bg-info">Request Headers</h5>
                                        <div class="table-responsive">
                                            <table class="table table-bordered">
                                            <thead class="thead-light text-center"><tr><th>Header Name</th><th>Header Value</th></tr></thead>
                                                <tbody>
                                                    <tr>
                                                        <td class="text-nowrap">User-Agent</td>
                                                        <td class="text-wrap">PostmanRuntime/7.37.1</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Accept</td>
                                                        <td class="text-wrap">*/*</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Cache-Control</td>
                                                        <td class="text-wrap">no-cache</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Postman-Token</td>
                                                        <td class="text-wrap">d3e978f9-3265-4b02-b7f6-2360082ac16f</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Host</td>
                                                        <td class="text-wrap">rahulshettyacademy.com</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Accept-Encoding</td>
                                                        <td class="text-wrap">gzip, deflate, br</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Connection</td>
                                                        <td class="text-wrap">keep-alive</td>
                                                    </tr>
                                                </tbody>
                                            </table>
                                        </div>
                                    </div>
                                </div>
                                </div>
                            </div>
                        </div>
                        <div class="row">
                        <div class="col-sm-12 mb-3">
                            <div class="card-deck">
                            <div class="card border-info" style="width: 50rem;">
                                <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Response Headers</h5>
                                    <div class="table-responsive">
                                        <table class="table table-bordered">
                                        <thead class="thead-light text-center"><tr><th>Header Name</th><th>Header Value</th></tr></thead>
                                            <tbody>
                                                <tr>
                                                    <td class="text-nowrap">Date</td>
                                                    <td class="text-wrap">Mon, 25 Mar 2024 11:05:01 GMT</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Server</td>
                                                    <td class="text-wrap">Apache/2.4.52 (Ubuntu)</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Access-Control-Allow-Origin</td>
                                                    <td class="text-wrap">*</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Access-Control-Allow-Methods</td>
                                                    <td class="text-wrap">POST</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Access-Control-Max-Age</td>
                                                    <td class="text-wrap">3600</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Access-Control-Allow-Headers</td>
                                                    <td class="text-wrap">Content-Type, Access-Control-Allow-Headers, Authorization, X-Requested-With</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Content-Length</td>
                                                    <td class="text-wrap">99</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Keep-Alive</td>
                                                    <td class="text-wrap">timeout&#x3D;5, max&#x3D;91</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Connection</td>
                                                    <td class="text-wrap">Keep-Alive</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Content-Type</td>
                                                    <td class="text-wrap">application/json;charset&#x3D;UTF-8</td>
                                                </tr>
                                            </tbody>
                                        </table>
                                    </div>
                                </div>
                            </div>
                            </div>
                        </div>
                        </div>
                        <div class="row">
                        <div class="col-sm-12 mb-3">
                            <div class="card-deck">
                            <div class="card border-info" style="width: 50rem;">
                                <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Response Body</h5>
                                        <div class="dyn-height">
                                                <pre><code id="copyText-909a8cbf-6e67-4645-87b1-f46ac9717948" class="prettyPrint">[{&quot;book_name&quot;:&quot;Python for Ethical Hacking&quot;,&quot;isbn&quot;:&quot;YC471&quot;,&quot;aisle&quot;:&quot;296&quot;,&quot;author&quot;:&quot;Maximo Fritsch&quot;}]</code></pre>
                                        </div>
                                        <div class="card-footer">
                                            <button class="btn btn-outline-secondary btn-sm copyButton" type="button" data-clipboard-action="copy" data-clipboard-target="#copyText-909a8cbf-6e67-4645-87b1-f46ac9717948">Copy to Clipboard</button>
                                        </div>
                                </div>
                            </div>
                            </div>
                            </div>
                        </div>
                        <div class="row">
                            <div class="card border-info">
                                <div class="card-body">
                                <h5 class="card-title text-uppercase text-white text-center bg-info">Test Information</h5>
                                    <div class="table-responsive text-nowrap">
                                        <table class="datatable table table-hover">
                                        <thead><tr class="text-center"><th>Name</th><th>Passed</th><th>Failed</th><th>Skipped</th></tr></thead>
                                            <tbody>
                                                <tr >
                                                    <td >Validation of status code 200</td>
                                                    <td class="text-center bg-success">1</td>
                                                    <td class="text-center ">0</td>
                                                    <td class="text-center ">0</td>
                                                </tr>
                                                <tr >
                                                    <td >Validation of response jason schema</td>
                                                    <td class="text-center bg-success">1</td>
                                                    <td class="text-center ">0</td>
                                                    <td class="text-center ">0</td>
                                                </tr>
                                                <tr >
                                                    <td >validation of  aisle and Author name </td>
                                                    <td class="text-center bg-success">1</td>
                                                    <td class="text-center ">0</td>
                                                    <td class="text-center ">0</td>
                                                </tr>
                                            </tbody>
                                            <tfoot>
                                                <tr class="bg-light">
                                                    <td><strong>Total</strong></td>
                                                    <td class="text-center">3</td>
                                                    <td class="text-center">0</td>
                                                    <td class="text-center">0</td>
                                                </tr>
                                            </tfoot>
                                        </table>
                                    </div>
                                    <div class="row d-none">
                                    <div class="col-sm-12 mb-3">
                                        <div class="card-deck">
                                        <div class="card border-danger" style="width: 50rem;">
                                            <div class="card-body">
                                                <h5 class="card-title text-uppercase text-white text-center bg-danger">Test Failure</h5>
                                                <div class="table-responsive">
                                                    <table class="table table-hover">
                                                    <thead><tr class="text-nowrap"><th>Test Name</th><th>Assertion Error</th></tr></thead>
                                                        <tbody>
                                                        </tbody>
                                                    </table>
                                                </div>
                                            </div>
                                        </div>
                                        </div>
                                    </div>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                    </div>
                </div>
                </div>
            </div>
            </div>
            <div id="folder-981b34af-54f8-4c7c-898a-6cdff3294434" class="card-deck iteration-2">
            <div class="row iteration-2">
                <div class="col-sm-12 mb-3 iteration-2">
                <div class="card iteration-2">
                    <div class="card-header  bg-success iteration-2">
                        <a data-toggle="collapse" href="#" data-target="#collapse-981b34af-54f8-4c7c-898a-6cdff3294434" aria-expanded="false" aria-controls="collapse" id="requests-981b34af-54f8-4c7c-898a-6cdff3294434" class="collapsed text-white z-block">
                    Iteration: 3 - GetBookByAuthor <i class="float-lg-right fa fa-chevron-down" style="padding-top: 5px;"></i>
                </a>
                    </div>
                    <div id="collapse-981b34af-54f8-4c7c-898a-6cdff3294434" class="collapse" aria-labelledby="requests-981b34af-54f8-4c7c-898a-6cdff3294434">
                    <div class="card-body">
                        <div class="row">
                            <div class="col-sm-12 mb-3">
                                <div class="card-deck">
                                <div class="card border-info" style="width: 50rem;">
                                    <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Request Information</h5>
                                    <span><i class="fas fa-info-circle"></i></span><strong> Request Method:</strong> <span class="badge-outline-success badge badge-success"> GET</span><br>
                                    <span><i class="fas fa-info-circle"></i></span><strong> Request URL:</strong> <a href="https://rahulshettyacademy.com/Library/GetBook.php?AuthorName&#x3D;Maximo%20Fritsch" target="_blank">https://rahulshettyacademy.com/Library/GetBook.php?AuthorName&#x3D;Maximo%20Fritsch</a><br>
                                    </div>
                                </div>
                                <div class="card border-info" style="width: 50rem;">
                                    <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Response Information</h5>
                                    <span><i class="fas fa-info-circle"></i></span><strong> Response Code:</strong> <span class="float-right badge-outline badge badge-success"> 200 - OK</span><br>
                                    <span><i class="fas fa-stopwatch"></i></span><strong> Mean time per request:</strong> <span class="float-right badge-outline badge badge-success"> 135ms</span><br>
                                    <span><i class="fas fa-database"></i></span><strong> Mean size per request:</strong> <span class="float-right badge-outline badge badge-success"> 73B</span><br>
                                    <hr>
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Test Pass Percentage</h5>
                                    <div>
                                        <div class="progress" style="height: 40px;">
                                            <div class="progress-bar bg-success" style="width: 100%" role="progressbar">
                                            <h5 class="text-uppercase text-white text-center" style="padding-top:5px;"><strong>No Tests for this request</strong></h5>
                                            </div>
                                        </div>
                                    </div>
                                    </div>
                                </div>
                            </div>
                            </div>
                        </div>
                        <div class="row">
                            <div class="col-sm-12 mb-3">
                                <div class="card-deck">
                                <div class="card border-info" style="width: 50rem;">
                                    <div class="card-body">
                                        <h5 class="card-title text-uppercase text-white text-center bg-info">Request Headers</h5>
                                        <div class="table-responsive">
                                            <table class="table table-bordered">
                                            <thead class="thead-light text-center"><tr><th>Header Name</th><th>Header Value</th></tr></thead>
                                                <tbody>
                                                    <tr>
                                                        <td class="text-nowrap">User-Agent</td>
                                                        <td class="text-wrap">PostmanRuntime/7.37.1</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Accept</td>
                                                        <td class="text-wrap">*/*</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Cache-Control</td>
                                                        <td class="text-wrap">no-cache</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Postman-Token</td>
                                                        <td class="text-wrap">e957d27f-2e2d-43b7-9b75-236d40107f3a</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Host</td>
                                                        <td class="text-wrap">rahulshettyacademy.com</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Accept-Encoding</td>
                                                        <td class="text-wrap">gzip, deflate, br</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Connection</td>
                                                        <td class="text-wrap">keep-alive</td>
                                                    </tr>
                                                </tbody>
                                            </table>
                                        </div>
                                    </div>
                                </div>
                                </div>
                            </div>
                        </div>
                        <div class="row">
                        <div class="col-sm-12 mb-3">
                            <div class="card-deck">
                            <div class="card border-info" style="width: 50rem;">
                                <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Response Headers</h5>
                                    <div class="table-responsive">
                                        <table class="table table-bordered">
                                        <thead class="thead-light text-center"><tr><th>Header Name</th><th>Header Value</th></tr></thead>
                                            <tbody>
                                                <tr>
                                                    <td class="text-nowrap">Date</td>
                                                    <td class="text-wrap">Mon, 25 Mar 2024 11:05:02 GMT</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Server</td>
                                                    <td class="text-wrap">Apache/2.4.52 (Ubuntu)</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Access-Control-Allow-Origin</td>
                                                    <td class="text-wrap">*</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Access-Control-Allow-Methods</td>
                                                    <td class="text-wrap">POST</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Access-Control-Max-Age</td>
                                                    <td class="text-wrap">3600</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Access-Control-Allow-Headers</td>
                                                    <td class="text-wrap">Content-Type, Access-Control-Allow-Headers, Authorization, X-Requested-With</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Content-Length</td>
                                                    <td class="text-wrap">73</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Keep-Alive</td>
                                                    <td class="text-wrap">timeout&#x3D;5, max&#x3D;90</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Connection</td>
                                                    <td class="text-wrap">Keep-Alive</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Content-Type</td>
                                                    <td class="text-wrap">application/json;charset&#x3D;UTF-8</td>
                                                </tr>
                                            </tbody>
                                        </table>
                                    </div>
                                </div>
                            </div>
                            </div>
                        </div>
                        </div>
                        <div class="row">
                        <div class="col-sm-12 mb-3">
                            <div class="card-deck">
                            <div class="card border-info" style="width: 50rem;">
                                <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Response Body</h5>
                                        <div class="dyn-height">
                                                <pre><code id="copyText-ac5ed8e1-a353-4a87-96f4-eed7aa1a66d6" class="prettyPrint">[{&quot;book_name&quot;:&quot;Python for Ethical Hacking&quot;,&quot;isbn&quot;:&quot;YC471&quot;,&quot;aisle&quot;:&quot;296&quot;}]</code></pre>
                                        </div>
                                        <div class="card-footer">
                                            <button class="btn btn-outline-secondary btn-sm copyButton" type="button" data-clipboard-action="copy" data-clipboard-target="#copyText-ac5ed8e1-a353-4a87-96f4-eed7aa1a66d6">Copy to Clipboard</button>
                                        </div>
                                </div>
                            </div>
                            </div>
                            </div>
                        </div>
                        <div class="row">
                            <div class="card border-info">
                                <div class="card-body">
                                <h5 class="card-title text-uppercase text-white text-center bg-info">Test Information</h5>
                                    <h5 class="alert alert-success text-uppercase text-center">No Tests for this request</h5>
                                </div>
                            </div>
                        </div>
                    </div>
                    </div>
                </div>
                </div>
            </div>
            </div>
            <div id="folder-a9ef9a9b-02b3-40c2-82c6-9d2edee1add1" class="card-deck iteration-2">
            <div class="row iteration-2">
                <div class="col-sm-12 mb-3 iteration-2">
                <div class="card iteration-2">
                    <div class="card-header  bg-success iteration-2">
                        <a data-toggle="collapse" href="#" data-target="#collapse-a9ef9a9b-02b3-40c2-82c6-9d2edee1add1" aria-expanded="false" aria-controls="collapse" id="requests-a9ef9a9b-02b3-40c2-82c6-9d2edee1add1" class="collapsed text-white z-block">
                    Iteration: 3 - DeleteBookByID <i class="float-lg-right fa fa-chevron-down" style="padding-top: 5px;"></i>
                </a>
                    </div>
                    <div id="collapse-a9ef9a9b-02b3-40c2-82c6-9d2edee1add1" class="collapse" aria-labelledby="requests-a9ef9a9b-02b3-40c2-82c6-9d2edee1add1">
                    <div class="card-body">
                        <div class="row">
                            <div class="col-sm-12 mb-3">
                                <div class="card-deck">
                                <div class="card border-info" style="width: 50rem;">
                                    <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Request Information</h5>
                                    <span><i class="fas fa-info-circle"></i></span><strong> Request Method:</strong> <span class="badge-outline-success badge badge-success"> POST</span><br>
                                    <span><i class="fas fa-info-circle"></i></span><strong> Request URL:</strong> <a href="https://rahulshettyacademy.com/Library/DeleteBook.php" target="_blank">https://rahulshettyacademy.com/Library/DeleteBook.php</a><br>
                                    </div>
                                </div>
                                <div class="card border-info" style="width: 50rem;">
                                    <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Response Information</h5>
                                    <span><i class="fas fa-info-circle"></i></span><strong> Response Code:</strong> <span class="float-right badge-outline badge badge-success"> 200 - OK</span><br>
                                    <span><i class="fas fa-stopwatch"></i></span><strong> Mean time per request:</strong> <span class="float-right badge-outline badge badge-success"> 96ms</span><br>
                                    <span><i class="fas fa-database"></i></span><strong> Mean size per request:</strong> <span class="float-right badge-outline badge badge-success"> 38B</span><br>
                                    <hr>
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Test Pass Percentage</h5>
                                    <div>
                                        <div class="progress" style="height: 40px;">
                                            <div class="progress-bar  bg-success" style="width: 100%" role="progressbar">
                                            <h5 style="padding-top:5px;"><strong>100 %</strong></h5>
                                            </div>
                                        </div>
                                    </div>
                                    </div>
                                </div>
                            </div>
                            </div>
                        </div>
                        <div class="row">
                            <div class="col-sm-12 mb-3">
                                <div class="card-deck">
                                <div class="card border-info" style="width: 50rem;">
                                    <div class="card-body">
                                        <h5 class="card-title text-uppercase text-white text-center bg-info">Request Headers</h5>
                                        <div class="table-responsive">
                                            <table class="table table-bordered">
                                            <thead class="thead-light text-center"><tr><th>Header Name</th><th>Header Value</th></tr></thead>
                                                <tbody>
                                                    <tr>
                                                        <td class="text-nowrap">Content-Type</td>
                                                        <td class="text-wrap">application/json</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">User-Agent</td>
                                                        <td class="text-wrap">PostmanRuntime/7.37.1</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Accept</td>
                                                        <td class="text-wrap">*/*</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Cache-Control</td>
                                                        <td class="text-wrap">no-cache</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Postman-Token</td>
                                                        <td class="text-wrap">0df8c96b-38f0-4171-973c-eda21561d69c</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Host</td>
                                                        <td class="text-wrap">rahulshettyacademy.com</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Accept-Encoding</td>
                                                        <td class="text-wrap">gzip, deflate, br</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Connection</td>
                                                        <td class="text-wrap">keep-alive</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Content-Length</td>
                                                        <td class="text-wrap">30</td>
                                                    </tr>
                                                </tbody>
                                            </table>
                                        </div>
                                    </div>
                                </div>
                                </div>
                            </div>
                        </div>
                        <div class="row">
                        <div class="col-sm-12 mb-3">
                            <div class="card-deck">
                            <div class="card border-info" style="width: 50rem;">
                                <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Request Body</h5>
                                        <div class="dyn-height">
                                            <pre><code id="copyReqText-3" class="prettyPrint">{
        
        &quot;ID&quot; : &quot;YC471296&quot;
         
        }
        </code></pre>
                                        </div>
                                        <div class="card-footer">
                                            <button class="btn btn-outline-secondary btn-sm copyButton" type="button" data-clipboard-action="copy" data-clipboard-target="#copyReqText-3">Copy to Clipboard</button>
                                        </div>
                                </div>
                            </div>
                            </div>
                        </div>
                        </div>
                        <div class="row">
                        <div class="col-sm-12 mb-3">
                            <div class="card-deck">
                            <div class="card border-info" style="width: 50rem;">
                                <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Response Headers</h5>
                                    <div class="table-responsive">
                                        <table class="table table-bordered">
                                        <thead class="thead-light text-center"><tr><th>Header Name</th><th>Header Value</th></tr></thead>
                                            <tbody>
                                                <tr>
                                                    <td class="text-nowrap">Date</td>
                                                    <td class="text-wrap">Mon, 25 Mar 2024 11:05:02 GMT</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Server</td>
                                                    <td class="text-wrap">Apache/2.4.52 (Ubuntu)</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Access-Control-Allow-Origin</td>
                                                    <td class="text-wrap">*</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Access-Control-Allow-Methods</td>
                                                    <td class="text-wrap">POST</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Access-Control-Max-Age</td>
                                                    <td class="text-wrap">3600</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Access-Control-Allow-Headers</td>
                                                    <td class="text-wrap">Content-Type, Access-Control-Allow-Headers, Authorization, X-Requested-With</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Content-Length</td>
                                                    <td class="text-wrap">38</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Keep-Alive</td>
                                                    <td class="text-wrap">timeout&#x3D;5, max&#x3D;89</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Connection</td>
                                                    <td class="text-wrap">Keep-Alive</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Content-Type</td>
                                                    <td class="text-wrap">application/json;charset&#x3D;UTF-8</td>
                                                </tr>
                                            </tbody>
                                        </table>
                                    </div>
                                </div>
                            </div>
                            </div>
                        </div>
                        </div>
                        <div class="row">
                        <div class="col-sm-12 mb-3">
                            <div class="card-deck">
                            <div class="card border-info" style="width: 50rem;">
                                <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Response Body</h5>
                                        <div class="dyn-height">
                                                <pre><code id="copyText-30e9c746-68d6-477c-b5b4-e99c496819dc" class="prettyPrint">{&quot;msg&quot;:&quot;book is successfully deleted&quot;}</code></pre>
                                        </div>
                                        <div class="card-footer">
                                            <button class="btn btn-outline-secondary btn-sm copyButton" type="button" data-clipboard-action="copy" data-clipboard-target="#copyText-30e9c746-68d6-477c-b5b4-e99c496819dc">Copy to Clipboard</button>
                                        </div>
                                </div>
                            </div>
                            </div>
                            </div>
                        </div>
                        <div class="row">
                            <div class="card border-info">
                                <div class="card-body">
                                <h5 class="card-title text-uppercase text-white text-center bg-info">Test Information</h5>
                                    <div class="table-responsive text-nowrap">
                                        <table class="datatable table table-hover">
                                        <thead><tr class="text-center"><th>Name</th><th>Passed</th><th>Failed</th><th>Skipped</th></tr></thead>
                                            <tbody>
                                                <tr >
                                                    <td >validation of successfully deleted</td>
                                                    <td class="text-center bg-success">1</td>
                                                    <td class="text-center ">0</td>
                                                    <td class="text-center ">0</td>
                                                </tr>
                                                <tr >
                                                    <td >Validation of status code 200</td>
                                                    <td class="text-center bg-success">1</td>
                                                    <td class="text-center ">0</td>
                                                    <td class="text-center ">0</td>
                                                </tr>
                                            </tbody>
                                            <tfoot>
                                                <tr class="bg-light">
                                                    <td><strong>Total</strong></td>
                                                    <td class="text-center">2</td>
                                                    <td class="text-center">0</td>
                                                    <td class="text-center">0</td>
                                                </tr>
                                            </tfoot>
                                        </table>
                                    </div>
                                    <div class="row d-none">
                                    <div class="col-sm-12 mb-3">
                                        <div class="card-deck">
                                        <div class="card border-danger" style="width: 50rem;">
                                            <div class="card-body">
                                                <h5 class="card-title text-uppercase text-white text-center bg-danger">Test Failure</h5>
                                                <div class="table-responsive">
                                                    <table class="table table-hover">
                                                    <thead><tr class="text-nowrap"><th>Test Name</th><th>Assertion Error</th></tr></thead>
                                                        <tbody>
                                                        </tbody>
                                                    </table>
                                                </div>
                                            </div>
                                        </div>
                                        </div>
                                    </div>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                    </div>
                </div>
                </div>
            </div>
            </div>
            <div id="folder-e930847c-a100-4520-99bb-704d04c45abb" class="card-deck iteration-3">
            <div class="row iteration-3">
                <div class="col-sm-12 mb-3 iteration-3">
                <div class="card iteration-3">
                    <div class="card-header  bg-success iteration-3">
                        <a data-toggle="collapse" href="#" data-target="#collapse-e930847c-a100-4520-99bb-704d04c45abb" aria-expanded="false" aria-controls="collapse" id="requests-e930847c-a100-4520-99bb-704d04c45abb" class="collapsed text-white z-block">
                    Iteration: 4 - AddBook <i class="float-lg-right fa fa-chevron-down" style="padding-top: 5px;"></i>
                </a>
                    </div>
                    <div id="collapse-e930847c-a100-4520-99bb-704d04c45abb" class="collapse" aria-labelledby="requests-e930847c-a100-4520-99bb-704d04c45abb">
                    <div class="card-body">
                        <div class="row">
                            <div class="col-sm-12 mb-3">
                                <div class="card-deck">
                                <div class="card border-info" style="width: 50rem;">
                                    <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Request Information</h5>
                                    <span><i class="fas fa-info-circle"></i></span><strong> Request Method:</strong> <span class="badge-outline-success badge badge-success"> GET</span><br>
                                    <span><i class="fas fa-info-circle"></i></span><strong> Request URL:</strong> <a href="https://rahulshettyacademy.com/Library/Addbook.php" target="_blank">https://rahulshettyacademy.com/Library/Addbook.php</a><br>
                                    </div>
                                </div>
                                <div class="card border-info" style="width: 50rem;">
                                    <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Response Information</h5>
                                    <span><i class="fas fa-info-circle"></i></span><strong> Response Code:</strong> <span class="float-right badge-outline badge badge-success"> 200 - OK</span><br>
                                    <span><i class="fas fa-stopwatch"></i></span><strong> Mean time per request:</strong> <span class="float-right badge-outline badge badge-success"> 105ms</span><br>
                                    <span><i class="fas fa-database"></i></span><strong> Mean size per request:</strong> <span class="float-right badge-outline badge badge-success"> 44B</span><br>
                                    <hr>
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Test Pass Percentage</h5>
                                    <div>
                                        <div class="progress" style="height: 40px;">
                                            <div class="progress-bar  bg-success" style="width: 100%" role="progressbar">
                                            <h5 style="padding-top:5px;"><strong>100 %</strong></h5>
                                            </div>
                                        </div>
                                    </div>
                                    </div>
                                </div>
                            </div>
                            </div>
                        </div>
                        <div class="row">
                            <div class="col-sm-12 mb-3">
                                <div class="card-deck">
                                <div class="card border-info" style="width: 50rem;">
                                    <div class="card-body">
                                        <h5 class="card-title text-uppercase text-white text-center bg-info">Request Headers</h5>
                                        <div class="table-responsive">
                                            <table class="table table-bordered">
                                            <thead class="thead-light text-center"><tr><th>Header Name</th><th>Header Value</th></tr></thead>
                                                <tbody>
                                                    <tr>
                                                        <td class="text-nowrap">Content-Type</td>
                                                        <td class="text-wrap">application/json</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">User-Agent</td>
                                                        <td class="text-wrap">PostmanRuntime/7.37.1</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Accept</td>
                                                        <td class="text-wrap">*/*</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Cache-Control</td>
                                                        <td class="text-wrap">no-cache</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Postman-Token</td>
                                                        <td class="text-wrap">50ed94ca-fe76-4ea8-b0c4-65f669269624</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Host</td>
                                                        <td class="text-wrap">rahulshettyacademy.com</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Accept-Encoding</td>
                                                        <td class="text-wrap">gzip, deflate, br</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Connection</td>
                                                        <td class="text-wrap">keep-alive</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Content-Length</td>
                                                        <td class="text-wrap">107</td>
                                                    </tr>
                                                </tbody>
                                            </table>
                                        </div>
                                    </div>
                                </div>
                                </div>
                            </div>
                        </div>
                        <div class="row">
                        <div class="col-sm-12 mb-3">
                            <div class="card-deck">
                            <div class="card border-info" style="width: 50rem;">
                                <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Request Body</h5>
                                        <div class="dyn-height">
                                            <pre><code id="copyReqText-0" class="prettyPrint">{
        
        &quot;name&quot;:&quot;Python for Ethical Hacking&quot;,
        &quot;isbn&quot;:&quot;YC382&quot;,
        &quot;aisle&quot;:&quot;704&quot;,
        &quot;author&quot;:&quot;Hillary Klein&quot;
        }
        
        </code></pre>
                                        </div>
                                        <div class="card-footer">
                                            <button class="btn btn-outline-secondary btn-sm copyButton" type="button" data-clipboard-action="copy" data-clipboard-target="#copyReqText-0">Copy to Clipboard</button>
                                        </div>
                                </div>
                            </div>
                            </div>
                        </div>
                        </div>
                        <div class="row">
                        <div class="col-sm-12 mb-3">
                            <div class="card-deck">
                            <div class="card border-info" style="width: 50rem;">
                                <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Response Headers</h5>
                                    <div class="table-responsive">
                                        <table class="table table-bordered">
                                        <thead class="thead-light text-center"><tr><th>Header Name</th><th>Header Value</th></tr></thead>
                                            <tbody>
                                                <tr>
                                                    <td class="text-nowrap">Date</td>
                                                    <td class="text-wrap">Mon, 25 Mar 2024 11:05:02 GMT</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Server</td>
                                                    <td class="text-wrap">Apache/2.4.52 (Ubuntu)</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Access-Control-Allow-Origin</td>
                                                    <td class="text-wrap">*</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Access-Control-Allow-Methods</td>
                                                    <td class="text-wrap">POST</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Access-Control-Max-Age</td>
                                                    <td class="text-wrap">3600</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Access-Control-Allow-Headers</td>
                                                    <td class="text-wrap">Content-Type, Access-Control-Allow-Headers, Authorization, X-Requested-With</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Content-Length</td>
                                                    <td class="text-wrap">44</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Keep-Alive</td>
                                                    <td class="text-wrap">timeout&#x3D;5, max&#x3D;88</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Connection</td>
                                                    <td class="text-wrap">Keep-Alive</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Content-Type</td>
                                                    <td class="text-wrap">application/json;charset&#x3D;UTF-8</td>
                                                </tr>
                                            </tbody>
                                        </table>
                                    </div>
                                </div>
                            </div>
                            </div>
                        </div>
                        </div>
                        <div class="row">
                        <div class="col-sm-12 mb-3">
                            <div class="card-deck">
                            <div class="card border-info" style="width: 50rem;">
                                <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Response Body</h5>
                                        <div class="dyn-height">
                                                <pre><code id="copyText-cc6d406a-a829-4cde-b988-3df674dae181" class="prettyPrint">{&quot;Msg&quot;:&quot;successfully added&quot;,&quot;ID&quot;:&quot;YC382704&quot;}</code></pre>
                                        </div>
                                        <div class="card-footer">
                                            <button class="btn btn-outline-secondary btn-sm copyButton" type="button" data-clipboard-action="copy" data-clipboard-target="#copyText-cc6d406a-a829-4cde-b988-3df674dae181">Copy to Clipboard</button>
                                        </div>
                                </div>
                            </div>
                            </div>
                            </div>
                        </div>
                        <div class="row">
                            <div class="card border-info">
                                <div class="card-body">
                                <h5 class="card-title text-uppercase text-white text-center bg-info">Test Information</h5>
                                    <div class="table-responsive text-nowrap">
                                        <table class="datatable table table-hover">
                                        <thead><tr class="text-center"><th>Name</th><th>Passed</th><th>Failed</th><th>Skipped</th></tr></thead>
                                            <tbody>
                                                <tr >
                                                    <td >Validation of status code 200</td>
                                                    <td class="text-center bg-success">1</td>
                                                    <td class="text-center ">0</td>
                                                    <td class="text-center ">0</td>
                                                </tr>
                                                <tr >
                                                    <td >Validation of response jason schema</td>
                                                    <td class="text-center bg-success">1</td>
                                                    <td class="text-center ">0</td>
                                                    <td class="text-center ">0</td>
                                                </tr>
                                                <tr >
                                                    <td >validation of successfully added</td>
                                                    <td class="text-center bg-success">1</td>
                                                    <td class="text-center ">0</td>
                                                    <td class="text-center ">0</td>
                                                </tr>
                                                <tr >
                                                    <td >Validation of Respose time below 1600</td>
                                                    <td class="text-center bg-success">1</td>
                                                    <td class="text-center ">0</td>
                                                    <td class="text-center ">0</td>
                                                </tr>
                                            </tbody>
                                            <tfoot>
                                                <tr class="bg-light">
                                                    <td><strong>Total</strong></td>
                                                    <td class="text-center">4</td>
                                                    <td class="text-center">0</td>
                                                    <td class="text-center">0</td>
                                                </tr>
                                            </tfoot>
                                        </table>
                                    </div>
                                    <div class="row d-none">
                                    <div class="col-sm-12 mb-3">
                                        <div class="card-deck">
                                        <div class="card border-danger" style="width: 50rem;">
                                            <div class="card-body">
                                                <h5 class="card-title text-uppercase text-white text-center bg-danger">Test Failure</h5>
                                                <div class="table-responsive">
                                                    <table class="table table-hover">
                                                    <thead><tr class="text-nowrap"><th>Test Name</th><th>Assertion Error</th></tr></thead>
                                                        <tbody>
                                                        </tbody>
                                                    </table>
                                                </div>
                                            </div>
                                        </div>
                                        </div>
                                    </div>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                    </div>
                </div>
                </div>
            </div>
            </div>
            <div id="folder-b181bed5-6d99-4a35-84df-7cd129d33b4d" class="card-deck iteration-3">
            <div class="row iteration-3">
                <div class="col-sm-12 mb-3 iteration-3">
                <div class="card iteration-3">
                    <div class="card-header  bg-success iteration-3">
                        <a data-toggle="collapse" href="#" data-target="#collapse-b181bed5-6d99-4a35-84df-7cd129d33b4d" aria-expanded="false" aria-controls="collapse" id="requests-b181bed5-6d99-4a35-84df-7cd129d33b4d" class="collapsed text-white z-block">
                    Iteration: 4 - GetBookByID <i class="float-lg-right fa fa-chevron-down" style="padding-top: 5px;"></i>
                </a>
                    </div>
                    <div id="collapse-b181bed5-6d99-4a35-84df-7cd129d33b4d" class="collapse" aria-labelledby="requests-b181bed5-6d99-4a35-84df-7cd129d33b4d">
                    <div class="card-body">
                        <div class="row">
                            <div class="col-sm-12 mb-3">
                                <div class="card-deck">
                                <div class="card border-info" style="width: 50rem;">
                                    <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Request Information</h5>
                                    <span><i class="fas fa-info-circle"></i></span><strong> Request Method:</strong> <span class="badge-outline-success badge badge-success"> GET</span><br>
                                    <span><i class="fas fa-info-circle"></i></span><strong> Request URL:</strong> <a href="https://rahulshettyacademy.com/Library/GetBook.php?ID&#x3D;YC382704" target="_blank">https://rahulshettyacademy.com/Library/GetBook.php?ID&#x3D;YC382704</a><br>
                                    </div>
                                </div>
                                <div class="card border-info" style="width: 50rem;">
                                    <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Response Information</h5>
                                    <span><i class="fas fa-info-circle"></i></span><strong> Response Code:</strong> <span class="float-right badge-outline badge badge-success"> 200 - OK</span><br>
                                    <span><i class="fas fa-stopwatch"></i></span><strong> Mean time per request:</strong> <span class="float-right badge-outline badge badge-success"> 90ms</span><br>
                                    <span><i class="fas fa-database"></i></span><strong> Mean size per request:</strong> <span class="float-right badge-outline badge badge-success"> 98B</span><br>
                                    <hr>
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Test Pass Percentage</h5>
                                    <div>
                                        <div class="progress" style="height: 40px;">
                                            <div class="progress-bar  bg-success" style="width: 100%" role="progressbar">
                                            <h5 style="padding-top:5px;"><strong>100 %</strong></h5>
                                            </div>
                                        </div>
                                    </div>
                                    </div>
                                </div>
                            </div>
                            </div>
                        </div>
                        <div class="row">
                            <div class="col-sm-12 mb-3">
                                <div class="card-deck">
                                <div class="card border-info" style="width: 50rem;">
                                    <div class="card-body">
                                        <h5 class="card-title text-uppercase text-white text-center bg-info">Request Headers</h5>
                                        <div class="table-responsive">
                                            <table class="table table-bordered">
                                            <thead class="thead-light text-center"><tr><th>Header Name</th><th>Header Value</th></tr></thead>
                                                <tbody>
                                                    <tr>
                                                        <td class="text-nowrap">User-Agent</td>
                                                        <td class="text-wrap">PostmanRuntime/7.37.1</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Accept</td>
                                                        <td class="text-wrap">*/*</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Cache-Control</td>
                                                        <td class="text-wrap">no-cache</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Postman-Token</td>
                                                        <td class="text-wrap">f6f5b05f-825b-45f8-bc37-65b050ba36da</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Host</td>
                                                        <td class="text-wrap">rahulshettyacademy.com</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Accept-Encoding</td>
                                                        <td class="text-wrap">gzip, deflate, br</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Connection</td>
                                                        <td class="text-wrap">keep-alive</td>
                                                    </tr>
                                                </tbody>
                                            </table>
                                        </div>
                                    </div>
                                </div>
                                </div>
                            </div>
                        </div>
                        <div class="row">
                        <div class="col-sm-12 mb-3">
                            <div class="card-deck">
                            <div class="card border-info" style="width: 50rem;">
                                <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Response Headers</h5>
                                    <div class="table-responsive">
                                        <table class="table table-bordered">
                                        <thead class="thead-light text-center"><tr><th>Header Name</th><th>Header Value</th></tr></thead>
                                            <tbody>
                                                <tr>
                                                    <td class="text-nowrap">Date</td>
                                                    <td class="text-wrap">Mon, 25 Mar 2024 11:05:02 GMT</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Server</td>
                                                    <td class="text-wrap">Apache/2.4.52 (Ubuntu)</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Access-Control-Allow-Origin</td>
                                                    <td class="text-wrap">*</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Access-Control-Allow-Methods</td>
                                                    <td class="text-wrap">POST</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Access-Control-Max-Age</td>
                                                    <td class="text-wrap">3600</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Access-Control-Allow-Headers</td>
                                                    <td class="text-wrap">Content-Type, Access-Control-Allow-Headers, Authorization, X-Requested-With</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Content-Length</td>
                                                    <td class="text-wrap">98</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Keep-Alive</td>
                                                    <td class="text-wrap">timeout&#x3D;5, max&#x3D;87</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Connection</td>
                                                    <td class="text-wrap">Keep-Alive</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Content-Type</td>
                                                    <td class="text-wrap">application/json;charset&#x3D;UTF-8</td>
                                                </tr>
                                            </tbody>
                                        </table>
                                    </div>
                                </div>
                            </div>
                            </div>
                        </div>
                        </div>
                        <div class="row">
                        <div class="col-sm-12 mb-3">
                            <div class="card-deck">
                            <div class="card border-info" style="width: 50rem;">
                                <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Response Body</h5>
                                        <div class="dyn-height">
                                                <pre><code id="copyText-909a8cbf-6e67-4645-87b1-f46ac9717948" class="prettyPrint">[{&quot;book_name&quot;:&quot;Python for Ethical Hacking&quot;,&quot;isbn&quot;:&quot;YC382&quot;,&quot;aisle&quot;:&quot;704&quot;,&quot;author&quot;:&quot;Hillary Klein&quot;}]</code></pre>
                                        </div>
                                        <div class="card-footer">
                                            <button class="btn btn-outline-secondary btn-sm copyButton" type="button" data-clipboard-action="copy" data-clipboard-target="#copyText-909a8cbf-6e67-4645-87b1-f46ac9717948">Copy to Clipboard</button>
                                        </div>
                                </div>
                            </div>
                            </div>
                            </div>
                        </div>
                        <div class="row">
                            <div class="card border-info">
                                <div class="card-body">
                                <h5 class="card-title text-uppercase text-white text-center bg-info">Test Information</h5>
                                    <div class="table-responsive text-nowrap">
                                        <table class="datatable table table-hover">
                                        <thead><tr class="text-center"><th>Name</th><th>Passed</th><th>Failed</th><th>Skipped</th></tr></thead>
                                            <tbody>
                                                <tr >
                                                    <td >Validation of status code 200</td>
                                                    <td class="text-center bg-success">1</td>
                                                    <td class="text-center ">0</td>
                                                    <td class="text-center ">0</td>
                                                </tr>
                                                <tr >
                                                    <td >Validation of response jason schema</td>
                                                    <td class="text-center bg-success">1</td>
                                                    <td class="text-center ">0</td>
                                                    <td class="text-center ">0</td>
                                                </tr>
                                                <tr >
                                                    <td >validation of  aisle and Author name </td>
                                                    <td class="text-center bg-success">1</td>
                                                    <td class="text-center ">0</td>
                                                    <td class="text-center ">0</td>
                                                </tr>
                                            </tbody>
                                            <tfoot>
                                                <tr class="bg-light">
                                                    <td><strong>Total</strong></td>
                                                    <td class="text-center">3</td>
                                                    <td class="text-center">0</td>
                                                    <td class="text-center">0</td>
                                                </tr>
                                            </tfoot>
                                        </table>
                                    </div>
                                    <div class="row d-none">
                                    <div class="col-sm-12 mb-3">
                                        <div class="card-deck">
                                        <div class="card border-danger" style="width: 50rem;">
                                            <div class="card-body">
                                                <h5 class="card-title text-uppercase text-white text-center bg-danger">Test Failure</h5>
                                                <div class="table-responsive">
                                                    <table class="table table-hover">
                                                    <thead><tr class="text-nowrap"><th>Test Name</th><th>Assertion Error</th></tr></thead>
                                                        <tbody>
                                                        </tbody>
                                                    </table>
                                                </div>
                                            </div>
                                        </div>
                                        </div>
                                    </div>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                    </div>
                </div>
                </div>
            </div>
            </div>
            <div id="folder-5bd82adb-c1c7-4361-9d4f-67f234bc6ee1" class="card-deck iteration-3">
            <div class="row iteration-3">
                <div class="col-sm-12 mb-3 iteration-3">
                <div class="card iteration-3">
                    <div class="card-header  bg-success iteration-3">
                        <a data-toggle="collapse" href="#" data-target="#collapse-5bd82adb-c1c7-4361-9d4f-67f234bc6ee1" aria-expanded="false" aria-controls="collapse" id="requests-5bd82adb-c1c7-4361-9d4f-67f234bc6ee1" class="collapsed text-white z-block">
                    Iteration: 4 - GetBookByAuthor <i class="float-lg-right fa fa-chevron-down" style="padding-top: 5px;"></i>
                </a>
                    </div>
                    <div id="collapse-5bd82adb-c1c7-4361-9d4f-67f234bc6ee1" class="collapse" aria-labelledby="requests-5bd82adb-c1c7-4361-9d4f-67f234bc6ee1">
                    <div class="card-body">
                        <div class="row">
                            <div class="col-sm-12 mb-3">
                                <div class="card-deck">
                                <div class="card border-info" style="width: 50rem;">
                                    <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Request Information</h5>
                                    <span><i class="fas fa-info-circle"></i></span><strong> Request Method:</strong> <span class="badge-outline-success badge badge-success"> GET</span><br>
                                    <span><i class="fas fa-info-circle"></i></span><strong> Request URL:</strong> <a href="https://rahulshettyacademy.com/Library/GetBook.php?AuthorName&#x3D;Hillary%20Klein" target="_blank">https://rahulshettyacademy.com/Library/GetBook.php?AuthorName&#x3D;Hillary%20Klein</a><br>
                                    </div>
                                </div>
                                <div class="card border-info" style="width: 50rem;">
                                    <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Response Information</h5>
                                    <span><i class="fas fa-info-circle"></i></span><strong> Response Code:</strong> <span class="float-right badge-outline badge badge-success"> 200 - OK</span><br>
                                    <span><i class="fas fa-stopwatch"></i></span><strong> Mean time per request:</strong> <span class="float-right badge-outline badge badge-success"> 144ms</span><br>
                                    <span><i class="fas fa-database"></i></span><strong> Mean size per request:</strong> <span class="float-right badge-outline badge badge-success"> 73B</span><br>
                                    <hr>
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Test Pass Percentage</h5>
                                    <div>
                                        <div class="progress" style="height: 40px;">
                                            <div class="progress-bar bg-success" style="width: 100%" role="progressbar">
                                            <h5 class="text-uppercase text-white text-center" style="padding-top:5px;"><strong>No Tests for this request</strong></h5>
                                            </div>
                                        </div>
                                    </div>
                                    </div>
                                </div>
                            </div>
                            </div>
                        </div>
                        <div class="row">
                            <div class="col-sm-12 mb-3">
                                <div class="card-deck">
                                <div class="card border-info" style="width: 50rem;">
                                    <div class="card-body">
                                        <h5 class="card-title text-uppercase text-white text-center bg-info">Request Headers</h5>
                                        <div class="table-responsive">
                                            <table class="table table-bordered">
                                            <thead class="thead-light text-center"><tr><th>Header Name</th><th>Header Value</th></tr></thead>
                                                <tbody>
                                                    <tr>
                                                        <td class="text-nowrap">User-Agent</td>
                                                        <td class="text-wrap">PostmanRuntime/7.37.1</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Accept</td>
                                                        <td class="text-wrap">*/*</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Cache-Control</td>
                                                        <td class="text-wrap">no-cache</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Postman-Token</td>
                                                        <td class="text-wrap">3f09c76f-1542-47b8-aa15-9797576a8a61</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Host</td>
                                                        <td class="text-wrap">rahulshettyacademy.com</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Accept-Encoding</td>
                                                        <td class="text-wrap">gzip, deflate, br</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Connection</td>
                                                        <td class="text-wrap">keep-alive</td>
                                                    </tr>
                                                </tbody>
                                            </table>
                                        </div>
                                    </div>
                                </div>
                                </div>
                            </div>
                        </div>
                        <div class="row">
                        <div class="col-sm-12 mb-3">
                            <div class="card-deck">
                            <div class="card border-info" style="width: 50rem;">
                                <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Response Headers</h5>
                                    <div class="table-responsive">
                                        <table class="table table-bordered">
                                        <thead class="thead-light text-center"><tr><th>Header Name</th><th>Header Value</th></tr></thead>
                                            <tbody>
                                                <tr>
                                                    <td class="text-nowrap">Date</td>
                                                    <td class="text-wrap">Mon, 25 Mar 2024 11:05:02 GMT</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Server</td>
                                                    <td class="text-wrap">Apache/2.4.52 (Ubuntu)</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Access-Control-Allow-Origin</td>
                                                    <td class="text-wrap">*</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Access-Control-Allow-Methods</td>
                                                    <td class="text-wrap">POST</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Access-Control-Max-Age</td>
                                                    <td class="text-wrap">3600</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Access-Control-Allow-Headers</td>
                                                    <td class="text-wrap">Content-Type, Access-Control-Allow-Headers, Authorization, X-Requested-With</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Content-Length</td>
                                                    <td class="text-wrap">73</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Keep-Alive</td>
                                                    <td class="text-wrap">timeout&#x3D;5, max&#x3D;86</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Connection</td>
                                                    <td class="text-wrap">Keep-Alive</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Content-Type</td>
                                                    <td class="text-wrap">application/json;charset&#x3D;UTF-8</td>
                                                </tr>
                                            </tbody>
                                        </table>
                                    </div>
                                </div>
                            </div>
                            </div>
                        </div>
                        </div>
                        <div class="row">
                        <div class="col-sm-12 mb-3">
                            <div class="card-deck">
                            <div class="card border-info" style="width: 50rem;">
                                <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Response Body</h5>
                                        <div class="dyn-height">
                                                <pre><code id="copyText-ac5ed8e1-a353-4a87-96f4-eed7aa1a66d6" class="prettyPrint">[{&quot;book_name&quot;:&quot;Python for Ethical Hacking&quot;,&quot;isbn&quot;:&quot;YC382&quot;,&quot;aisle&quot;:&quot;704&quot;}]</code></pre>
                                        </div>
                                        <div class="card-footer">
                                            <button class="btn btn-outline-secondary btn-sm copyButton" type="button" data-clipboard-action="copy" data-clipboard-target="#copyText-ac5ed8e1-a353-4a87-96f4-eed7aa1a66d6">Copy to Clipboard</button>
                                        </div>
                                </div>
                            </div>
                            </div>
                            </div>
                        </div>
                        <div class="row">
                            <div class="card border-info">
                                <div class="card-body">
                                <h5 class="card-title text-uppercase text-white text-center bg-info">Test Information</h5>
                                    <h5 class="alert alert-success text-uppercase text-center">No Tests for this request</h5>
                                </div>
                            </div>
                        </div>
                    </div>
                    </div>
                </div>
                </div>
            </div>
            </div>
            <div id="folder-ca2f42b9-cf8d-44bd-b09e-86294afec322" class="card-deck iteration-3">
            <div class="row iteration-3">
                <div class="col-sm-12 mb-3 iteration-3">
                <div class="card iteration-3">
                    <div class="card-header  bg-success iteration-3">
                        <a data-toggle="collapse" href="#" data-target="#collapse-ca2f42b9-cf8d-44bd-b09e-86294afec322" aria-expanded="false" aria-controls="collapse" id="requests-ca2f42b9-cf8d-44bd-b09e-86294afec322" class="collapsed text-white z-block">
                    Iteration: 4 - DeleteBookByID <i class="float-lg-right fa fa-chevron-down" style="padding-top: 5px;"></i>
                </a>
                    </div>
                    <div id="collapse-ca2f42b9-cf8d-44bd-b09e-86294afec322" class="collapse" aria-labelledby="requests-ca2f42b9-cf8d-44bd-b09e-86294afec322">
                    <div class="card-body">
                        <div class="row">
                            <div class="col-sm-12 mb-3">
                                <div class="card-deck">
                                <div class="card border-info" style="width: 50rem;">
                                    <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Request Information</h5>
                                    <span><i class="fas fa-info-circle"></i></span><strong> Request Method:</strong> <span class="badge-outline-success badge badge-success"> POST</span><br>
                                    <span><i class="fas fa-info-circle"></i></span><strong> Request URL:</strong> <a href="https://rahulshettyacademy.com/Library/DeleteBook.php" target="_blank">https://rahulshettyacademy.com/Library/DeleteBook.php</a><br>
                                    </div>
                                </div>
                                <div class="card border-info" style="width: 50rem;">
                                    <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Response Information</h5>
                                    <span><i class="fas fa-info-circle"></i></span><strong> Response Code:</strong> <span class="float-right badge-outline badge badge-success"> 200 - OK</span><br>
                                    <span><i class="fas fa-stopwatch"></i></span><strong> Mean time per request:</strong> <span class="float-right badge-outline badge badge-success"> 97ms</span><br>
                                    <span><i class="fas fa-database"></i></span><strong> Mean size per request:</strong> <span class="float-right badge-outline badge badge-success"> 38B</span><br>
                                    <hr>
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Test Pass Percentage</h5>
                                    <div>
                                        <div class="progress" style="height: 40px;">
                                            <div class="progress-bar  bg-success" style="width: 100%" role="progressbar">
                                            <h5 style="padding-top:5px;"><strong>100 %</strong></h5>
                                            </div>
                                        </div>
                                    </div>
                                    </div>
                                </div>
                            </div>
                            </div>
                        </div>
                        <div class="row">
                            <div class="col-sm-12 mb-3">
                                <div class="card-deck">
                                <div class="card border-info" style="width: 50rem;">
                                    <div class="card-body">
                                        <h5 class="card-title text-uppercase text-white text-center bg-info">Request Headers</h5>
                                        <div class="table-responsive">
                                            <table class="table table-bordered">
                                            <thead class="thead-light text-center"><tr><th>Header Name</th><th>Header Value</th></tr></thead>
                                                <tbody>
                                                    <tr>
                                                        <td class="text-nowrap">Content-Type</td>
                                                        <td class="text-wrap">application/json</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">User-Agent</td>
                                                        <td class="text-wrap">PostmanRuntime/7.37.1</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Accept</td>
                                                        <td class="text-wrap">*/*</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Cache-Control</td>
                                                        <td class="text-wrap">no-cache</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Postman-Token</td>
                                                        <td class="text-wrap">72fe8fcf-84a3-4364-b6de-83e9fcec2ad6</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Host</td>
                                                        <td class="text-wrap">rahulshettyacademy.com</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Accept-Encoding</td>
                                                        <td class="text-wrap">gzip, deflate, br</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Connection</td>
                                                        <td class="text-wrap">keep-alive</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Content-Length</td>
                                                        <td class="text-wrap">30</td>
                                                    </tr>
                                                </tbody>
                                            </table>
                                        </div>
                                    </div>
                                </div>
                                </div>
                            </div>
                        </div>
                        <div class="row">
                        <div class="col-sm-12 mb-3">
                            <div class="card-deck">
                            <div class="card border-info" style="width: 50rem;">
                                <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Request Body</h5>
                                        <div class="dyn-height">
                                            <pre><code id="copyReqText-3" class="prettyPrint">{
        
        &quot;ID&quot; : &quot;YC382704&quot;
         
        }
        </code></pre>
                                        </div>
                                        <div class="card-footer">
                                            <button class="btn btn-outline-secondary btn-sm copyButton" type="button" data-clipboard-action="copy" data-clipboard-target="#copyReqText-3">Copy to Clipboard</button>
                                        </div>
                                </div>
                            </div>
                            </div>
                        </div>
                        </div>
                        <div class="row">
                        <div class="col-sm-12 mb-3">
                            <div class="card-deck">
                            <div class="card border-info" style="width: 50rem;">
                                <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Response Headers</h5>
                                    <div class="table-responsive">
                                        <table class="table table-bordered">
                                        <thead class="thead-light text-center"><tr><th>Header Name</th><th>Header Value</th></tr></thead>
                                            <tbody>
                                                <tr>
                                                    <td class="text-nowrap">Date</td>
                                                    <td class="text-wrap">Mon, 25 Mar 2024 11:05:03 GMT</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Server</td>
                                                    <td class="text-wrap">Apache/2.4.52 (Ubuntu)</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Access-Control-Allow-Origin</td>
                                                    <td class="text-wrap">*</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Access-Control-Allow-Methods</td>
                                                    <td class="text-wrap">POST</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Access-Control-Max-Age</td>
                                                    <td class="text-wrap">3600</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Access-Control-Allow-Headers</td>
                                                    <td class="text-wrap">Content-Type, Access-Control-Allow-Headers, Authorization, X-Requested-With</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Content-Length</td>
                                                    <td class="text-wrap">38</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Keep-Alive</td>
                                                    <td class="text-wrap">timeout&#x3D;5, max&#x3D;85</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Connection</td>
                                                    <td class="text-wrap">Keep-Alive</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Content-Type</td>
                                                    <td class="text-wrap">application/json;charset&#x3D;UTF-8</td>
                                                </tr>
                                            </tbody>
                                        </table>
                                    </div>
                                </div>
                            </div>
                            </div>
                        </div>
                        </div>
                        <div class="row">
                        <div class="col-sm-12 mb-3">
                            <div class="card-deck">
                            <div class="card border-info" style="width: 50rem;">
                                <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Response Body</h5>
                                        <div class="dyn-height">
                                                <pre><code id="copyText-30e9c746-68d6-477c-b5b4-e99c496819dc" class="prettyPrint">{&quot;msg&quot;:&quot;book is successfully deleted&quot;}</code></pre>
                                        </div>
                                        <div class="card-footer">
                                            <button class="btn btn-outline-secondary btn-sm copyButton" type="button" data-clipboard-action="copy" data-clipboard-target="#copyText-30e9c746-68d6-477c-b5b4-e99c496819dc">Copy to Clipboard</button>
                                        </div>
                                </div>
                            </div>
                            </div>
                            </div>
                        </div>
                        <div class="row">
                            <div class="card border-info">
                                <div class="card-body">
                                <h5 class="card-title text-uppercase text-white text-center bg-info">Test Information</h5>
                                    <div class="table-responsive text-nowrap">
                                        <table class="datatable table table-hover">
                                        <thead><tr class="text-center"><th>Name</th><th>Passed</th><th>Failed</th><th>Skipped</th></tr></thead>
                                            <tbody>
                                                <tr >
                                                    <td >validation of successfully deleted</td>
                                                    <td class="text-center bg-success">1</td>
                                                    <td class="text-center ">0</td>
                                                    <td class="text-center ">0</td>
                                                </tr>
                                                <tr >
                                                    <td >Validation of status code 200</td>
                                                    <td class="text-center bg-success">1</td>
                                                    <td class="text-center ">0</td>
                                                    <td class="text-center ">0</td>
                                                </tr>
                                            </tbody>
                                            <tfoot>
                                                <tr class="bg-light">
                                                    <td><strong>Total</strong></td>
                                                    <td class="text-center">2</td>
                                                    <td class="text-center">0</td>
                                                    <td class="text-center">0</td>
                                                </tr>
                                            </tfoot>
                                        </table>
                                    </div>
                                    <div class="row d-none">
                                    <div class="col-sm-12 mb-3">
                                        <div class="card-deck">
                                        <div class="card border-danger" style="width: 50rem;">
                                            <div class="card-body">
                                                <h5 class="card-title text-uppercase text-white text-center bg-danger">Test Failure</h5>
                                                <div class="table-responsive">
                                                    <table class="table table-hover">
                                                    <thead><tr class="text-nowrap"><th>Test Name</th><th>Assertion Error</th></tr></thead>
                                                        <tbody>
                                                        </tbody>
                                                    </table>
                                                </div>
                                            </div>
                                        </div>
                                        </div>
                                    </div>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                    </div>
                </div>
                </div>
            </div>
            </div>
            <div id="folder-84990463-cadd-4b69-8da7-2c23687cad7b" class="card-deck iteration-4">
            <div class="row iteration-4">
                <div class="col-sm-12 mb-3 iteration-4">
                <div class="card iteration-4">
                    <div class="card-header  bg-success iteration-4">
                        <a data-toggle="collapse" href="#" data-target="#collapse-84990463-cadd-4b69-8da7-2c23687cad7b" aria-expanded="false" aria-controls="collapse" id="requests-84990463-cadd-4b69-8da7-2c23687cad7b" class="collapsed text-white z-block">
                    Iteration: 5 - AddBook <i class="float-lg-right fa fa-chevron-down" style="padding-top: 5px;"></i>
                </a>
                    </div>
                    <div id="collapse-84990463-cadd-4b69-8da7-2c23687cad7b" class="collapse" aria-labelledby="requests-84990463-cadd-4b69-8da7-2c23687cad7b">
                    <div class="card-body">
                        <div class="row">
                            <div class="col-sm-12 mb-3">
                                <div class="card-deck">
                                <div class="card border-info" style="width: 50rem;">
                                    <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Request Information</h5>
                                    <span><i class="fas fa-info-circle"></i></span><strong> Request Method:</strong> <span class="badge-outline-success badge badge-success"> GET</span><br>
                                    <span><i class="fas fa-info-circle"></i></span><strong> Request URL:</strong> <a href="https://rahulshettyacademy.com/Library/Addbook.php" target="_blank">https://rahulshettyacademy.com/Library/Addbook.php</a><br>
                                    </div>
                                </div>
                                <div class="card border-info" style="width: 50rem;">
                                    <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Response Information</h5>
                                    <span><i class="fas fa-info-circle"></i></span><strong> Response Code:</strong> <span class="float-right badge-outline badge badge-success"> 200 - OK</span><br>
                                    <span><i class="fas fa-stopwatch"></i></span><strong> Mean time per request:</strong> <span class="float-right badge-outline badge badge-success"> 96ms</span><br>
                                    <span><i class="fas fa-database"></i></span><strong> Mean size per request:</strong> <span class="float-right badge-outline badge badge-success"> 44B</span><br>
                                    <hr>
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Test Pass Percentage</h5>
                                    <div>
                                        <div class="progress" style="height: 40px;">
                                            <div class="progress-bar  bg-success" style="width: 100%" role="progressbar">
                                            <h5 style="padding-top:5px;"><strong>100 %</strong></h5>
                                            </div>
                                        </div>
                                    </div>
                                    </div>
                                </div>
                            </div>
                            </div>
                        </div>
                        <div class="row">
                            <div class="col-sm-12 mb-3">
                                <div class="card-deck">
                                <div class="card border-info" style="width: 50rem;">
                                    <div class="card-body">
                                        <h5 class="card-title text-uppercase text-white text-center bg-info">Request Headers</h5>
                                        <div class="table-responsive">
                                            <table class="table table-bordered">
                                            <thead class="thead-light text-center"><tr><th>Header Name</th><th>Header Value</th></tr></thead>
                                                <tbody>
                                                    <tr>
                                                        <td class="text-nowrap">Content-Type</td>
                                                        <td class="text-wrap">application/json</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">User-Agent</td>
                                                        <td class="text-wrap">PostmanRuntime/7.37.1</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Accept</td>
                                                        <td class="text-wrap">*/*</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Cache-Control</td>
                                                        <td class="text-wrap">no-cache</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Postman-Token</td>
                                                        <td class="text-wrap">b14c51ac-5bf3-4c9f-b1b4-4a30dd4ef9c3</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Host</td>
                                                        <td class="text-wrap">rahulshettyacademy.com</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Accept-Encoding</td>
                                                        <td class="text-wrap">gzip, deflate, br</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Connection</td>
                                                        <td class="text-wrap">keep-alive</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Content-Length</td>
                                                        <td class="text-wrap">106</td>
                                                    </tr>
                                                </tbody>
                                            </table>
                                        </div>
                                    </div>
                                </div>
                                </div>
                            </div>
                        </div>
                        <div class="row">
                        <div class="col-sm-12 mb-3">
                            <div class="card-deck">
                            <div class="card border-info" style="width: 50rem;">
                                <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Request Body</h5>
                                        <div class="dyn-height">
                                            <pre><code id="copyReqText-0" class="prettyPrint">{
        
        &quot;name&quot;:&quot;Python for Ethical Hacking&quot;,
        &quot;isbn&quot;:&quot;YC902&quot;,
        &quot;aisle&quot;:&quot;785&quot;,
        &quot;author&quot;:&quot;Martina Feil&quot;
        }
        
        </code></pre>
                                        </div>
                                        <div class="card-footer">
                                            <button class="btn btn-outline-secondary btn-sm copyButton" type="button" data-clipboard-action="copy" data-clipboard-target="#copyReqText-0">Copy to Clipboard</button>
                                        </div>
                                </div>
                            </div>
                            </div>
                        </div>
                        </div>
                        <div class="row">
                        <div class="col-sm-12 mb-3">
                            <div class="card-deck">
                            <div class="card border-info" style="width: 50rem;">
                                <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Response Headers</h5>
                                    <div class="table-responsive">
                                        <table class="table table-bordered">
                                        <thead class="thead-light text-center"><tr><th>Header Name</th><th>Header Value</th></tr></thead>
                                            <tbody>
                                                <tr>
                                                    <td class="text-nowrap">Date</td>
                                                    <td class="text-wrap">Mon, 25 Mar 2024 11:05:03 GMT</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Server</td>
                                                    <td class="text-wrap">Apache/2.4.52 (Ubuntu)</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Access-Control-Allow-Origin</td>
                                                    <td class="text-wrap">*</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Access-Control-Allow-Methods</td>
                                                    <td class="text-wrap">POST</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Access-Control-Max-Age</td>
                                                    <td class="text-wrap">3600</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Access-Control-Allow-Headers</td>
                                                    <td class="text-wrap">Content-Type, Access-Control-Allow-Headers, Authorization, X-Requested-With</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Content-Length</td>
                                                    <td class="text-wrap">44</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Keep-Alive</td>
                                                    <td class="text-wrap">timeout&#x3D;5, max&#x3D;84</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Connection</td>
                                                    <td class="text-wrap">Keep-Alive</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Content-Type</td>
                                                    <td class="text-wrap">application/json;charset&#x3D;UTF-8</td>
                                                </tr>
                                            </tbody>
                                        </table>
                                    </div>
                                </div>
                            </div>
                            </div>
                        </div>
                        </div>
                        <div class="row">
                        <div class="col-sm-12 mb-3">
                            <div class="card-deck">
                            <div class="card border-info" style="width: 50rem;">
                                <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Response Body</h5>
                                        <div class="dyn-height">
                                                <pre><code id="copyText-cc6d406a-a829-4cde-b988-3df674dae181" class="prettyPrint">{&quot;Msg&quot;:&quot;successfully added&quot;,&quot;ID&quot;:&quot;YC902785&quot;}</code></pre>
                                        </div>
                                        <div class="card-footer">
                                            <button class="btn btn-outline-secondary btn-sm copyButton" type="button" data-clipboard-action="copy" data-clipboard-target="#copyText-cc6d406a-a829-4cde-b988-3df674dae181">Copy to Clipboard</button>
                                        </div>
                                </div>
                            </div>
                            </div>
                            </div>
                        </div>
                        <div class="row">
                            <div class="card border-info">
                                <div class="card-body">
                                <h5 class="card-title text-uppercase text-white text-center bg-info">Test Information</h5>
                                    <div class="table-responsive text-nowrap">
                                        <table class="datatable table table-hover">
                                        <thead><tr class="text-center"><th>Name</th><th>Passed</th><th>Failed</th><th>Skipped</th></tr></thead>
                                            <tbody>
                                                <tr >
                                                    <td >Validation of status code 200</td>
                                                    <td class="text-center bg-success">1</td>
                                                    <td class="text-center ">0</td>
                                                    <td class="text-center ">0</td>
                                                </tr>
                                                <tr >
                                                    <td >Validation of response jason schema</td>
                                                    <td class="text-center bg-success">1</td>
                                                    <td class="text-center ">0</td>
                                                    <td class="text-center ">0</td>
                                                </tr>
                                                <tr >
                                                    <td >validation of successfully added</td>
                                                    <td class="text-center bg-success">1</td>
                                                    <td class="text-center ">0</td>
                                                    <td class="text-center ">0</td>
                                                </tr>
                                                <tr >
                                                    <td >Validation of Respose time below 1600</td>
                                                    <td class="text-center bg-success">1</td>
                                                    <td class="text-center ">0</td>
                                                    <td class="text-center ">0</td>
                                                </tr>
                                            </tbody>
                                            <tfoot>
                                                <tr class="bg-light">
                                                    <td><strong>Total</strong></td>
                                                    <td class="text-center">4</td>
                                                    <td class="text-center">0</td>
                                                    <td class="text-center">0</td>
                                                </tr>
                                            </tfoot>
                                        </table>
                                    </div>
                                    <div class="row d-none">
                                    <div class="col-sm-12 mb-3">
                                        <div class="card-deck">
                                        <div class="card border-danger" style="width: 50rem;">
                                            <div class="card-body">
                                                <h5 class="card-title text-uppercase text-white text-center bg-danger">Test Failure</h5>
                                                <div class="table-responsive">
                                                    <table class="table table-hover">
                                                    <thead><tr class="text-nowrap"><th>Test Name</th><th>Assertion Error</th></tr></thead>
                                                        <tbody>
                                                        </tbody>
                                                    </table>
                                                </div>
                                            </div>
                                        </div>
                                        </div>
                                    </div>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                    </div>
                </div>
                </div>
            </div>
            </div>
            <div id="folder-58cf8178-9f7b-40e3-9e3b-63ef55bc42d5" class="card-deck iteration-4">
            <div class="row iteration-4">
                <div class="col-sm-12 mb-3 iteration-4">
                <div class="card iteration-4">
                    <div class="card-header  bg-success iteration-4">
                        <a data-toggle="collapse" href="#" data-target="#collapse-58cf8178-9f7b-40e3-9e3b-63ef55bc42d5" aria-expanded="false" aria-controls="collapse" id="requests-58cf8178-9f7b-40e3-9e3b-63ef55bc42d5" class="collapsed text-white z-block">
                    Iteration: 5 - GetBookByID <i class="float-lg-right fa fa-chevron-down" style="padding-top: 5px;"></i>
                </a>
                    </div>
                    <div id="collapse-58cf8178-9f7b-40e3-9e3b-63ef55bc42d5" class="collapse" aria-labelledby="requests-58cf8178-9f7b-40e3-9e3b-63ef55bc42d5">
                    <div class="card-body">
                        <div class="row">
                            <div class="col-sm-12 mb-3">
                                <div class="card-deck">
                                <div class="card border-info" style="width: 50rem;">
                                    <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Request Information</h5>
                                    <span><i class="fas fa-info-circle"></i></span><strong> Request Method:</strong> <span class="badge-outline-success badge badge-success"> GET</span><br>
                                    <span><i class="fas fa-info-circle"></i></span><strong> Request URL:</strong> <a href="https://rahulshettyacademy.com/Library/GetBook.php?ID&#x3D;YC902785" target="_blank">https://rahulshettyacademy.com/Library/GetBook.php?ID&#x3D;YC902785</a><br>
                                    </div>
                                </div>
                                <div class="card border-info" style="width: 50rem;">
                                    <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Response Information</h5>
                                    <span><i class="fas fa-info-circle"></i></span><strong> Response Code:</strong> <span class="float-right badge-outline badge badge-success"> 200 - OK</span><br>
                                    <span><i class="fas fa-stopwatch"></i></span><strong> Mean time per request:</strong> <span class="float-right badge-outline badge badge-success"> 89ms</span><br>
                                    <span><i class="fas fa-database"></i></span><strong> Mean size per request:</strong> <span class="float-right badge-outline badge badge-success"> 97B</span><br>
                                    <hr>
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Test Pass Percentage</h5>
                                    <div>
                                        <div class="progress" style="height: 40px;">
                                            <div class="progress-bar  bg-success" style="width: 100%" role="progressbar">
                                            <h5 style="padding-top:5px;"><strong>100 %</strong></h5>
                                            </div>
                                        </div>
                                    </div>
                                    </div>
                                </div>
                            </div>
                            </div>
                        </div>
                        <div class="row">
                            <div class="col-sm-12 mb-3">
                                <div class="card-deck">
                                <div class="card border-info" style="width: 50rem;">
                                    <div class="card-body">
                                        <h5 class="card-title text-uppercase text-white text-center bg-info">Request Headers</h5>
                                        <div class="table-responsive">
                                            <table class="table table-bordered">
                                            <thead class="thead-light text-center"><tr><th>Header Name</th><th>Header Value</th></tr></thead>
                                                <tbody>
                                                    <tr>
                                                        <td class="text-nowrap">User-Agent</td>
                                                        <td class="text-wrap">PostmanRuntime/7.37.1</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Accept</td>
                                                        <td class="text-wrap">*/*</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Cache-Control</td>
                                                        <td class="text-wrap">no-cache</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Postman-Token</td>
                                                        <td class="text-wrap">f0923c63-0768-4c61-ae8e-e89f061fe8c6</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Host</td>
                                                        <td class="text-wrap">rahulshettyacademy.com</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Accept-Encoding</td>
                                                        <td class="text-wrap">gzip, deflate, br</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Connection</td>
                                                        <td class="text-wrap">keep-alive</td>
                                                    </tr>
                                                </tbody>
                                            </table>
                                        </div>
                                    </div>
                                </div>
                                </div>
                            </div>
                        </div>
                        <div class="row">
                        <div class="col-sm-12 mb-3">
                            <div class="card-deck">
                            <div class="card border-info" style="width: 50rem;">
                                <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Response Headers</h5>
                                    <div class="table-responsive">
                                        <table class="table table-bordered">
                                        <thead class="thead-light text-center"><tr><th>Header Name</th><th>Header Value</th></tr></thead>
                                            <tbody>
                                                <tr>
                                                    <td class="text-nowrap">Date</td>
                                                    <td class="text-wrap">Mon, 25 Mar 2024 11:05:03 GMT</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Server</td>
                                                    <td class="text-wrap">Apache/2.4.52 (Ubuntu)</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Access-Control-Allow-Origin</td>
                                                    <td class="text-wrap">*</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Access-Control-Allow-Methods</td>
                                                    <td class="text-wrap">POST</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Access-Control-Max-Age</td>
                                                    <td class="text-wrap">3600</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Access-Control-Allow-Headers</td>
                                                    <td class="text-wrap">Content-Type, Access-Control-Allow-Headers, Authorization, X-Requested-With</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Content-Length</td>
                                                    <td class="text-wrap">97</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Keep-Alive</td>
                                                    <td class="text-wrap">timeout&#x3D;5, max&#x3D;83</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Connection</td>
                                                    <td class="text-wrap">Keep-Alive</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Content-Type</td>
                                                    <td class="text-wrap">application/json;charset&#x3D;UTF-8</td>
                                                </tr>
                                            </tbody>
                                        </table>
                                    </div>
                                </div>
                            </div>
                            </div>
                        </div>
                        </div>
                        <div class="row">
                        <div class="col-sm-12 mb-3">
                            <div class="card-deck">
                            <div class="card border-info" style="width: 50rem;">
                                <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Response Body</h5>
                                        <div class="dyn-height">
                                                <pre><code id="copyText-909a8cbf-6e67-4645-87b1-f46ac9717948" class="prettyPrint">[{&quot;book_name&quot;:&quot;Python for Ethical Hacking&quot;,&quot;isbn&quot;:&quot;YC902&quot;,&quot;aisle&quot;:&quot;785&quot;,&quot;author&quot;:&quot;Martina Feil&quot;}]</code></pre>
                                        </div>
                                        <div class="card-footer">
                                            <button class="btn btn-outline-secondary btn-sm copyButton" type="button" data-clipboard-action="copy" data-clipboard-target="#copyText-909a8cbf-6e67-4645-87b1-f46ac9717948">Copy to Clipboard</button>
                                        </div>
                                </div>
                            </div>
                            </div>
                            </div>
                        </div>
                        <div class="row">
                            <div class="card border-info">
                                <div class="card-body">
                                <h5 class="card-title text-uppercase text-white text-center bg-info">Test Information</h5>
                                    <div class="table-responsive text-nowrap">
                                        <table class="datatable table table-hover">
                                        <thead><tr class="text-center"><th>Name</th><th>Passed</th><th>Failed</th><th>Skipped</th></tr></thead>
                                            <tbody>
                                                <tr >
                                                    <td >Validation of status code 200</td>
                                                    <td class="text-center bg-success">1</td>
                                                    <td class="text-center ">0</td>
                                                    <td class="text-center ">0</td>
                                                </tr>
                                                <tr >
                                                    <td >Validation of response jason schema</td>
                                                    <td class="text-center bg-success">1</td>
                                                    <td class="text-center ">0</td>
                                                    <td class="text-center ">0</td>
                                                </tr>
                                                <tr >
                                                    <td >validation of  aisle and Author name </td>
                                                    <td class="text-center bg-success">1</td>
                                                    <td class="text-center ">0</td>
                                                    <td class="text-center ">0</td>
                                                </tr>
                                            </tbody>
                                            <tfoot>
                                                <tr class="bg-light">
                                                    <td><strong>Total</strong></td>
                                                    <td class="text-center">3</td>
                                                    <td class="text-center">0</td>
                                                    <td class="text-center">0</td>
                                                </tr>
                                            </tfoot>
                                        </table>
                                    </div>
                                    <div class="row d-none">
                                    <div class="col-sm-12 mb-3">
                                        <div class="card-deck">
                                        <div class="card border-danger" style="width: 50rem;">
                                            <div class="card-body">
                                                <h5 class="card-title text-uppercase text-white text-center bg-danger">Test Failure</h5>
                                                <div class="table-responsive">
                                                    <table class="table table-hover">
                                                    <thead><tr class="text-nowrap"><th>Test Name</th><th>Assertion Error</th></tr></thead>
                                                        <tbody>
                                                        </tbody>
                                                    </table>
                                                </div>
                                            </div>
                                        </div>
                                        </div>
                                    </div>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                    </div>
                </div>
                </div>
            </div>
            </div>
            <div id="folder-9ad94586-de84-4544-bcfc-18fe0d3eb21b" class="card-deck iteration-4">
            <div class="row iteration-4">
                <div class="col-sm-12 mb-3 iteration-4">
                <div class="card iteration-4">
                    <div class="card-header  bg-success iteration-4">
                        <a data-toggle="collapse" href="#" data-target="#collapse-9ad94586-de84-4544-bcfc-18fe0d3eb21b" aria-expanded="false" aria-controls="collapse" id="requests-9ad94586-de84-4544-bcfc-18fe0d3eb21b" class="collapsed text-white z-block">
                    Iteration: 5 - GetBookByAuthor <i class="float-lg-right fa fa-chevron-down" style="padding-top: 5px;"></i>
                </a>
                    </div>
                    <div id="collapse-9ad94586-de84-4544-bcfc-18fe0d3eb21b" class="collapse" aria-labelledby="requests-9ad94586-de84-4544-bcfc-18fe0d3eb21b">
                    <div class="card-body">
                        <div class="row">
                            <div class="col-sm-12 mb-3">
                                <div class="card-deck">
                                <div class="card border-info" style="width: 50rem;">
                                    <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Request Information</h5>
                                    <span><i class="fas fa-info-circle"></i></span><strong> Request Method:</strong> <span class="badge-outline-success badge badge-success"> GET</span><br>
                                    <span><i class="fas fa-info-circle"></i></span><strong> Request URL:</strong> <a href="https://rahulshettyacademy.com/Library/GetBook.php?AuthorName&#x3D;Martina%20Feil" target="_blank">https://rahulshettyacademy.com/Library/GetBook.php?AuthorName&#x3D;Martina%20Feil</a><br>
                                    </div>
                                </div>
                                <div class="card border-info" style="width: 50rem;">
                                    <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Response Information</h5>
                                    <span><i class="fas fa-info-circle"></i></span><strong> Response Code:</strong> <span class="float-right badge-outline badge badge-success"> 200 - OK</span><br>
                                    <span><i class="fas fa-stopwatch"></i></span><strong> Mean time per request:</strong> <span class="float-right badge-outline badge badge-success"> 127ms</span><br>
                                    <span><i class="fas fa-database"></i></span><strong> Mean size per request:</strong> <span class="float-right badge-outline badge badge-success"> 73B</span><br>
                                    <hr>
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Test Pass Percentage</h5>
                                    <div>
                                        <div class="progress" style="height: 40px;">
                                            <div class="progress-bar bg-success" style="width: 100%" role="progressbar">
                                            <h5 class="text-uppercase text-white text-center" style="padding-top:5px;"><strong>No Tests for this request</strong></h5>
                                            </div>
                                        </div>
                                    </div>
                                    </div>
                                </div>
                            </div>
                            </div>
                        </div>
                        <div class="row">
                            <div class="col-sm-12 mb-3">
                                <div class="card-deck">
                                <div class="card border-info" style="width: 50rem;">
                                    <div class="card-body">
                                        <h5 class="card-title text-uppercase text-white text-center bg-info">Request Headers</h5>
                                        <div class="table-responsive">
                                            <table class="table table-bordered">
                                            <thead class="thead-light text-center"><tr><th>Header Name</th><th>Header Value</th></tr></thead>
                                                <tbody>
                                                    <tr>
                                                        <td class="text-nowrap">User-Agent</td>
                                                        <td class="text-wrap">PostmanRuntime/7.37.1</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Accept</td>
                                                        <td class="text-wrap">*/*</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Cache-Control</td>
                                                        <td class="text-wrap">no-cache</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Postman-Token</td>
                                                        <td class="text-wrap">a6525414-0898-4729-947b-13168bc342d9</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Host</td>
                                                        <td class="text-wrap">rahulshettyacademy.com</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Accept-Encoding</td>
                                                        <td class="text-wrap">gzip, deflate, br</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Connection</td>
                                                        <td class="text-wrap">keep-alive</td>
                                                    </tr>
                                                </tbody>
                                            </table>
                                        </div>
                                    </div>
                                </div>
                                </div>
                            </div>
                        </div>
                        <div class="row">
                        <div class="col-sm-12 mb-3">
                            <div class="card-deck">
                            <div class="card border-info" style="width: 50rem;">
                                <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Response Headers</h5>
                                    <div class="table-responsive">
                                        <table class="table table-bordered">
                                        <thead class="thead-light text-center"><tr><th>Header Name</th><th>Header Value</th></tr></thead>
                                            <tbody>
                                                <tr>
                                                    <td class="text-nowrap">Date</td>
                                                    <td class="text-wrap">Mon, 25 Mar 2024 11:05:03 GMT</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Server</td>
                                                    <td class="text-wrap">Apache/2.4.52 (Ubuntu)</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Access-Control-Allow-Origin</td>
                                                    <td class="text-wrap">*</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Access-Control-Allow-Methods</td>
                                                    <td class="text-wrap">POST</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Access-Control-Max-Age</td>
                                                    <td class="text-wrap">3600</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Access-Control-Allow-Headers</td>
                                                    <td class="text-wrap">Content-Type, Access-Control-Allow-Headers, Authorization, X-Requested-With</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Content-Length</td>
                                                    <td class="text-wrap">73</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Keep-Alive</td>
                                                    <td class="text-wrap">timeout&#x3D;5, max&#x3D;82</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Connection</td>
                                                    <td class="text-wrap">Keep-Alive</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Content-Type</td>
                                                    <td class="text-wrap">application/json;charset&#x3D;UTF-8</td>
                                                </tr>
                                            </tbody>
                                        </table>
                                    </div>
                                </div>
                            </div>
                            </div>
                        </div>
                        </div>
                        <div class="row">
                        <div class="col-sm-12 mb-3">
                            <div class="card-deck">
                            <div class="card border-info" style="width: 50rem;">
                                <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Response Body</h5>
                                        <div class="dyn-height">
                                                <pre><code id="copyText-ac5ed8e1-a353-4a87-96f4-eed7aa1a66d6" class="prettyPrint">[{&quot;book_name&quot;:&quot;Python for Ethical Hacking&quot;,&quot;isbn&quot;:&quot;YC902&quot;,&quot;aisle&quot;:&quot;785&quot;}]</code></pre>
                                        </div>
                                        <div class="card-footer">
                                            <button class="btn btn-outline-secondary btn-sm copyButton" type="button" data-clipboard-action="copy" data-clipboard-target="#copyText-ac5ed8e1-a353-4a87-96f4-eed7aa1a66d6">Copy to Clipboard</button>
                                        </div>
                                </div>
                            </div>
                            </div>
                            </div>
                        </div>
                        <div class="row">
                            <div class="card border-info">
                                <div class="card-body">
                                <h5 class="card-title text-uppercase text-white text-center bg-info">Test Information</h5>
                                    <h5 class="alert alert-success text-uppercase text-center">No Tests for this request</h5>
                                </div>
                            </div>
                        </div>
                    </div>
                    </div>
                </div>
                </div>
            </div>
            </div>
            <div id="folder-d55d10be-f15c-4fe2-b3eb-9399b0728fd3" class="card-deck iteration-4">
            <div class="row iteration-4">
                <div class="col-sm-12 mb-3 iteration-4">
                <div class="card iteration-4">
                    <div class="card-header  bg-success iteration-4">
                        <a data-toggle="collapse" href="#" data-target="#collapse-d55d10be-f15c-4fe2-b3eb-9399b0728fd3" aria-expanded="false" aria-controls="collapse" id="requests-d55d10be-f15c-4fe2-b3eb-9399b0728fd3" class="collapsed text-white z-block">
                    Iteration: 5 - DeleteBookByID <i class="float-lg-right fa fa-chevron-down" style="padding-top: 5px;"></i>
                </a>
                    </div>
                    <div id="collapse-d55d10be-f15c-4fe2-b3eb-9399b0728fd3" class="collapse" aria-labelledby="requests-d55d10be-f15c-4fe2-b3eb-9399b0728fd3">
                    <div class="card-body">
                        <div class="row">
                            <div class="col-sm-12 mb-3">
                                <div class="card-deck">
                                <div class="card border-info" style="width: 50rem;">
                                    <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Request Information</h5>
                                    <span><i class="fas fa-info-circle"></i></span><strong> Request Method:</strong> <span class="badge-outline-success badge badge-success"> POST</span><br>
                                    <span><i class="fas fa-info-circle"></i></span><strong> Request URL:</strong> <a href="https://rahulshettyacademy.com/Library/DeleteBook.php" target="_blank">https://rahulshettyacademy.com/Library/DeleteBook.php</a><br>
                                    </div>
                                </div>
                                <div class="card border-info" style="width: 50rem;">
                                    <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Response Information</h5>
                                    <span><i class="fas fa-info-circle"></i></span><strong> Response Code:</strong> <span class="float-right badge-outline badge badge-success"> 200 - OK</span><br>
                                    <span><i class="fas fa-stopwatch"></i></span><strong> Mean time per request:</strong> <span class="float-right badge-outline badge badge-success"> 95ms</span><br>
                                    <span><i class="fas fa-database"></i></span><strong> Mean size per request:</strong> <span class="float-right badge-outline badge badge-success"> 38B</span><br>
                                    <hr>
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Test Pass Percentage</h5>
                                    <div>
                                        <div class="progress" style="height: 40px;">
                                            <div class="progress-bar  bg-success" style="width: 100%" role="progressbar">
                                            <h5 style="padding-top:5px;"><strong>100 %</strong></h5>
                                            </div>
                                        </div>
                                    </div>
                                    </div>
                                </div>
                            </div>
                            </div>
                        </div>
                        <div class="row">
                            <div class="col-sm-12 mb-3">
                                <div class="card-deck">
                                <div class="card border-info" style="width: 50rem;">
                                    <div class="card-body">
                                        <h5 class="card-title text-uppercase text-white text-center bg-info">Request Headers</h5>
                                        <div class="table-responsive">
                                            <table class="table table-bordered">
                                            <thead class="thead-light text-center"><tr><th>Header Name</th><th>Header Value</th></tr></thead>
                                                <tbody>
                                                    <tr>
                                                        <td class="text-nowrap">Content-Type</td>
                                                        <td class="text-wrap">application/json</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">User-Agent</td>
                                                        <td class="text-wrap">PostmanRuntime/7.37.1</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Accept</td>
                                                        <td class="text-wrap">*/*</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Cache-Control</td>
                                                        <td class="text-wrap">no-cache</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Postman-Token</td>
                                                        <td class="text-wrap">7d78a29f-1dd2-4f2e-bb90-c21a70d39639</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Host</td>
                                                        <td class="text-wrap">rahulshettyacademy.com</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Accept-Encoding</td>
                                                        <td class="text-wrap">gzip, deflate, br</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Connection</td>
                                                        <td class="text-wrap">keep-alive</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Content-Length</td>
                                                        <td class="text-wrap">30</td>
                                                    </tr>
                                                </tbody>
                                            </table>
                                        </div>
                                    </div>
                                </div>
                                </div>
                            </div>
                        </div>
                        <div class="row">
                        <div class="col-sm-12 mb-3">
                            <div class="card-deck">
                            <div class="card border-info" style="width: 50rem;">
                                <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Request Body</h5>
                                        <div class="dyn-height">
                                            <pre><code id="copyReqText-3" class="prettyPrint">{
        
        &quot;ID&quot; : &quot;YC902785&quot;
         
        }
        </code></pre>
                                        </div>
                                        <div class="card-footer">
                                            <button class="btn btn-outline-secondary btn-sm copyButton" type="button" data-clipboard-action="copy" data-clipboard-target="#copyReqText-3">Copy to Clipboard</button>
                                        </div>
                                </div>
                            </div>
                            </div>
                        </div>
                        </div>
                        <div class="row">
                        <div class="col-sm-12 mb-3">
                            <div class="card-deck">
                            <div class="card border-info" style="width: 50rem;">
                                <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Response Headers</h5>
                                    <div class="table-responsive">
                                        <table class="table table-bordered">
                                        <thead class="thead-light text-center"><tr><th>Header Name</th><th>Header Value</th></tr></thead>
                                            <tbody>
                                                <tr>
                                                    <td class="text-nowrap">Date</td>
                                                    <td class="text-wrap">Mon, 25 Mar 2024 11:05:03 GMT</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Server</td>
                                                    <td class="text-wrap">Apache/2.4.52 (Ubuntu)</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Access-Control-Allow-Origin</td>
                                                    <td class="text-wrap">*</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Access-Control-Allow-Methods</td>
                                                    <td class="text-wrap">POST</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Access-Control-Max-Age</td>
                                                    <td class="text-wrap">3600</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Access-Control-Allow-Headers</td>
                                                    <td class="text-wrap">Content-Type, Access-Control-Allow-Headers, Authorization, X-Requested-With</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Content-Length</td>
                                                    <td class="text-wrap">38</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Keep-Alive</td>
                                                    <td class="text-wrap">timeout&#x3D;5, max&#x3D;81</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Connection</td>
                                                    <td class="text-wrap">Keep-Alive</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Content-Type</td>
                                                    <td class="text-wrap">application/json;charset&#x3D;UTF-8</td>
                                                </tr>
                                            </tbody>
                                        </table>
                                    </div>
                                </div>
                            </div>
                            </div>
                        </div>
                        </div>
                        <div class="row">
                        <div class="col-sm-12 mb-3">
                            <div class="card-deck">
                            <div class="card border-info" style="width: 50rem;">
                                <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Response Body</h5>
                                        <div class="dyn-height">
                                                <pre><code id="copyText-30e9c746-68d6-477c-b5b4-e99c496819dc" class="prettyPrint">{&quot;msg&quot;:&quot;book is successfully deleted&quot;}</code></pre>
                                        </div>
                                        <div class="card-footer">
                                            <button class="btn btn-outline-secondary btn-sm copyButton" type="button" data-clipboard-action="copy" data-clipboard-target="#copyText-30e9c746-68d6-477c-b5b4-e99c496819dc">Copy to Clipboard</button>
                                        </div>
                                </div>
                            </div>
                            </div>
                            </div>
                        </div>
                        <div class="row">
                            <div class="card border-info">
                                <div class="card-body">
                                <h5 class="card-title text-uppercase text-white text-center bg-info">Test Information</h5>
                                    <div class="table-responsive text-nowrap">
                                        <table class="datatable table table-hover">
                                        <thead><tr class="text-center"><th>Name</th><th>Passed</th><th>Failed</th><th>Skipped</th></tr></thead>
                                            <tbody>
                                                <tr >
                                                    <td >validation of successfully deleted</td>
                                                    <td class="text-center bg-success">1</td>
                                                    <td class="text-center ">0</td>
                                                    <td class="text-center ">0</td>
                                                </tr>
                                                <tr >
                                                    <td >Validation of status code 200</td>
                                                    <td class="text-center bg-success">1</td>
                                                    <td class="text-center ">0</td>
                                                    <td class="text-center ">0</td>
                                                </tr>
                                            </tbody>
                                            <tfoot>
                                                <tr class="bg-light">
                                                    <td><strong>Total</strong></td>
                                                    <td class="text-center">2</td>
                                                    <td class="text-center">0</td>
                                                    <td class="text-center">0</td>
                                                </tr>
                                            </tfoot>
                                        </table>
                                    </div>
                                    <div class="row d-none">
                                    <div class="col-sm-12 mb-3">
                                        <div class="card-deck">
                                        <div class="card border-danger" style="width: 50rem;">
                                            <div class="card-body">
                                                <h5 class="card-title text-uppercase text-white text-center bg-danger">Test Failure</h5>
                                                <div class="table-responsive">
                                                    <table class="table table-hover">
                                                    <thead><tr class="text-nowrap"><th>Test Name</th><th>Assertion Error</th></tr></thead>
                                                        <tbody>
                                                        </tbody>
                                                    </table>
                                                </div>
                                            </div>
                                        </div>
                                        </div>
                                    </div>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                    </div>
                </div>
                </div>
            </div>
            </div>
        </div>
    </div>
    </div>
    </div>
    </div>
    </div>


<script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/twitter-bootstrap/4.2.1/js/bootstrap.bundle.min.js"></script>
<script src="https://cdn.datatables.net/v/bs4/dt-1.10.18/datatables.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/clipboard.js/2.0.0/clipboard.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/remarkable/1.7.1/remarkable.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/highlight.js/10.1.2/highlight.min.js"></script>
<script>hljs.initHighlightingOnLoad();</script>

<!-- Set slider initial position depending on the localstorage state -->

<script>
(function () {
  var sliderChecked = true;
  if (localStorage.getItem('theme') === 'theme-light') {
    setTheme('theme-light');
    sliderChecked = false;
  } else {
    setTheme('theme-dark');
    sliderChecked = true;
  }
  $(document).ready( function () {
    document.getElementById('slider').checked = sliderChecked;
  });
})();
</script>

<!-- Data Table Configuration -->

<script>
$(document).ready( function () {
    $('.datatable').DataTable({
        "retrieve": true,
        "paging": false,
        "info": false,
        "fixedColumns":   {
            "heightMatch": 'none'
        }
    });
});
</script>

<!-- Tooltip Configuration -->

<script>
$(document).ready(function() {
    $('[data-toggle="tooltip"]').tooltip({
        trigger : 'hover'
    })
})
</script>

<!-- Show/Hide The Folders -->

<script>
$('#openAll').on('click', function(e) {
let clickCount = $(this).data("clickCount") || 1
switch (clickCount){
    case 1:
            $('#folder-14155408-857e-4cd7-ace1-42aacb6b01c7-iteration-0').removeClass('collapsed')
            $('#folder-collapse-14155408-857e-4cd7-ace1-42aacb6b01c7-iteration-0').addClass('show')
            $('#folder-14155408-857e-4cd7-ace1-42aacb6b01c7-iteration-1').removeClass('collapsed')
            $('#folder-collapse-14155408-857e-4cd7-ace1-42aacb6b01c7-iteration-1').addClass('show')
            $('#folder-14155408-857e-4cd7-ace1-42aacb6b01c7-iteration-2').removeClass('collapsed')
            $('#folder-collapse-14155408-857e-4cd7-ace1-42aacb6b01c7-iteration-2').addClass('show')
            $('#folder-14155408-857e-4cd7-ace1-42aacb6b01c7-iteration-3').removeClass('collapsed')
            $('#folder-collapse-14155408-857e-4cd7-ace1-42aacb6b01c7-iteration-3').addClass('show')
            $('#folder-14155408-857e-4cd7-ace1-42aacb6b01c7-iteration-4').removeClass('collapsed')
            $('#folder-collapse-14155408-857e-4cd7-ace1-42aacb6b01c7-iteration-4').addClass('show')
        $('#openAll').html("Collapse Folders");
        break;
    case 2:
            $('#folder-14155408-857e-4cd7-ace1-42aacb6b01c7-iteration-0').addClass('collapsed')
            $('#folder-collapse-14155408-857e-4cd7-ace1-42aacb6b01c7-iteration-0').removeClass('show')
            $('#folder-14155408-857e-4cd7-ace1-42aacb6b01c7-iteration-1').addClass('collapsed')
            $('#folder-collapse-14155408-857e-4cd7-ace1-42aacb6b01c7-iteration-1').removeClass('show')
            $('#folder-14155408-857e-4cd7-ace1-42aacb6b01c7-iteration-2').addClass('collapsed')
            $('#folder-collapse-14155408-857e-4cd7-ace1-42aacb6b01c7-iteration-2').removeClass('show')
            $('#folder-14155408-857e-4cd7-ace1-42aacb6b01c7-iteration-3').addClass('collapsed')
            $('#folder-collapse-14155408-857e-4cd7-ace1-42aacb6b01c7-iteration-3').removeClass('show')
            $('#folder-14155408-857e-4cd7-ace1-42aacb6b01c7-iteration-4').addClass('collapsed')
            $('#folder-collapse-14155408-857e-4cd7-ace1-42aacb6b01c7-iteration-4').removeClass('show')
        $('#openAll').html("Expand Folders");
        break;
}
clickCount = clickCount > 1 ? 1 : ++clickCount;
$(this).data("clickCount", clickCount)
})
</script>

<!-- Show/Hide The Requests -->

<script>
$('#openAllRequests').on('click', function(e) {
let clickCount = $(this).data("clickCount") || 1
switch (clickCount){
    case 1:
            $('#requests-39195611-8f6b-40de-b7a3-b0890ae57d82').removeClass('collapsed')
            $('#collapse-39195611-8f6b-40de-b7a3-b0890ae57d82').removeClass('collapsed')
            $('#requests-39195611-8f6b-40de-b7a3-b0890ae57d82').addClass('show')
            $('#collapse-39195611-8f6b-40de-b7a3-b0890ae57d82').addClass('show')
            $('#requests-6ee48502-c146-4da3-b82f-d978307eccc5').removeClass('collapsed')
            $('#collapse-6ee48502-c146-4da3-b82f-d978307eccc5').removeClass('collapsed')
            $('#requests-6ee48502-c146-4da3-b82f-d978307eccc5').addClass('show')
            $('#collapse-6ee48502-c146-4da3-b82f-d978307eccc5').addClass('show')
            $('#requests-c944e98b-5b4d-4bcf-b10e-b13dab6b891f').removeClass('collapsed')
            $('#collapse-c944e98b-5b4d-4bcf-b10e-b13dab6b891f').removeClass('collapsed')
            $('#requests-c944e98b-5b4d-4bcf-b10e-b13dab6b891f').addClass('show')
            $('#collapse-c944e98b-5b4d-4bcf-b10e-b13dab6b891f').addClass('show')
            $('#requests-19f23f22-f53f-4a0b-8f0f-38c012772a51').removeClass('collapsed')
            $('#collapse-19f23f22-f53f-4a0b-8f0f-38c012772a51').removeClass('collapsed')
            $('#requests-19f23f22-f53f-4a0b-8f0f-38c012772a51').addClass('show')
            $('#collapse-19f23f22-f53f-4a0b-8f0f-38c012772a51').addClass('show')
            $('#requests-a00c9dc5-6cf0-4c8a-9665-52645e4fea72').removeClass('collapsed')
            $('#collapse-a00c9dc5-6cf0-4c8a-9665-52645e4fea72').removeClass('collapsed')
            $('#requests-a00c9dc5-6cf0-4c8a-9665-52645e4fea72').addClass('show')
            $('#collapse-a00c9dc5-6cf0-4c8a-9665-52645e4fea72').addClass('show')
            $('#requests-3b722c97-19c8-4e4f-a755-13b24a54bc64').removeClass('collapsed')
            $('#collapse-3b722c97-19c8-4e4f-a755-13b24a54bc64').removeClass('collapsed')
            $('#requests-3b722c97-19c8-4e4f-a755-13b24a54bc64').addClass('show')
            $('#collapse-3b722c97-19c8-4e4f-a755-13b24a54bc64').addClass('show')
            $('#requests-aed24b74-a9e3-49bf-a498-ca699eb4ece5').removeClass('collapsed')
            $('#collapse-aed24b74-a9e3-49bf-a498-ca699eb4ece5').removeClass('collapsed')
            $('#requests-aed24b74-a9e3-49bf-a498-ca699eb4ece5').addClass('show')
            $('#collapse-aed24b74-a9e3-49bf-a498-ca699eb4ece5').addClass('show')
            $('#requests-70002bef-fd90-4087-9fe7-3f2c8fb58c17').removeClass('collapsed')
            $('#collapse-70002bef-fd90-4087-9fe7-3f2c8fb58c17').removeClass('collapsed')
            $('#requests-70002bef-fd90-4087-9fe7-3f2c8fb58c17').addClass('show')
            $('#collapse-70002bef-fd90-4087-9fe7-3f2c8fb58c17').addClass('show')
            $('#requests-06834e6a-2d58-44fd-a9b2-e1fe81325499').removeClass('collapsed')
            $('#collapse-06834e6a-2d58-44fd-a9b2-e1fe81325499').removeClass('collapsed')
            $('#requests-06834e6a-2d58-44fd-a9b2-e1fe81325499').addClass('show')
            $('#collapse-06834e6a-2d58-44fd-a9b2-e1fe81325499').addClass('show')
            $('#requests-c8d8247c-a1f3-4979-a236-cafd9f24c702').removeClass('collapsed')
            $('#collapse-c8d8247c-a1f3-4979-a236-cafd9f24c702').removeClass('collapsed')
            $('#requests-c8d8247c-a1f3-4979-a236-cafd9f24c702').addClass('show')
            $('#collapse-c8d8247c-a1f3-4979-a236-cafd9f24c702').addClass('show')
            $('#requests-981b34af-54f8-4c7c-898a-6cdff3294434').removeClass('collapsed')
            $('#collapse-981b34af-54f8-4c7c-898a-6cdff3294434').removeClass('collapsed')
            $('#requests-981b34af-54f8-4c7c-898a-6cdff3294434').addClass('show')
            $('#collapse-981b34af-54f8-4c7c-898a-6cdff3294434').addClass('show')
            $('#requests-a9ef9a9b-02b3-40c2-82c6-9d2edee1add1').removeClass('collapsed')
            $('#collapse-a9ef9a9b-02b3-40c2-82c6-9d2edee1add1').removeClass('collapsed')
            $('#requests-a9ef9a9b-02b3-40c2-82c6-9d2edee1add1').addClass('show')
            $('#collapse-a9ef9a9b-02b3-40c2-82c6-9d2edee1add1').addClass('show')
            $('#requests-e930847c-a100-4520-99bb-704d04c45abb').removeClass('collapsed')
            $('#collapse-e930847c-a100-4520-99bb-704d04c45abb').removeClass('collapsed')
            $('#requests-e930847c-a100-4520-99bb-704d04c45abb').addClass('show')
            $('#collapse-e930847c-a100-4520-99bb-704d04c45abb').addClass('show')
            $('#requests-b181bed5-6d99-4a35-84df-7cd129d33b4d').removeClass('collapsed')
            $('#collapse-b181bed5-6d99-4a35-84df-7cd129d33b4d').removeClass('collapsed')
            $('#requests-b181bed5-6d99-4a35-84df-7cd129d33b4d').addClass('show')
            $('#collapse-b181bed5-6d99-4a35-84df-7cd129d33b4d').addClass('show')
            $('#requests-5bd82adb-c1c7-4361-9d4f-67f234bc6ee1').removeClass('collapsed')
            $('#collapse-5bd82adb-c1c7-4361-9d4f-67f234bc6ee1').removeClass('collapsed')
            $('#requests-5bd82adb-c1c7-4361-9d4f-67f234bc6ee1').addClass('show')
            $('#collapse-5bd82adb-c1c7-4361-9d4f-67f234bc6ee1').addClass('show')
            $('#requests-ca2f42b9-cf8d-44bd-b09e-86294afec322').removeClass('collapsed')
            $('#collapse-ca2f42b9-cf8d-44bd-b09e-86294afec322').removeClass('collapsed')
            $('#requests-ca2f42b9-cf8d-44bd-b09e-86294afec322').addClass('show')
            $('#collapse-ca2f42b9-cf8d-44bd-b09e-86294afec322').addClass('show')
            $('#requests-84990463-cadd-4b69-8da7-2c23687cad7b').removeClass('collapsed')
            $('#collapse-84990463-cadd-4b69-8da7-2c23687cad7b').removeClass('collapsed')
            $('#requests-84990463-cadd-4b69-8da7-2c23687cad7b').addClass('show')
            $('#collapse-84990463-cadd-4b69-8da7-2c23687cad7b').addClass('show')
            $('#requests-58cf8178-9f7b-40e3-9e3b-63ef55bc42d5').removeClass('collapsed')
            $('#collapse-58cf8178-9f7b-40e3-9e3b-63ef55bc42d5').removeClass('collapsed')
            $('#requests-58cf8178-9f7b-40e3-9e3b-63ef55bc42d5').addClass('show')
            $('#collapse-58cf8178-9f7b-40e3-9e3b-63ef55bc42d5').addClass('show')
            $('#requests-9ad94586-de84-4544-bcfc-18fe0d3eb21b').removeClass('collapsed')
            $('#collapse-9ad94586-de84-4544-bcfc-18fe0d3eb21b').removeClass('collapsed')
            $('#requests-9ad94586-de84-4544-bcfc-18fe0d3eb21b').addClass('show')
            $('#collapse-9ad94586-de84-4544-bcfc-18fe0d3eb21b').addClass('show')
            $('#requests-d55d10be-f15c-4fe2-b3eb-9399b0728fd3').removeClass('collapsed')
            $('#collapse-d55d10be-f15c-4fe2-b3eb-9399b0728fd3').removeClass('collapsed')
            $('#requests-d55d10be-f15c-4fe2-b3eb-9399b0728fd3').addClass('show')
            $('#collapse-d55d10be-f15c-4fe2-b3eb-9399b0728fd3').addClass('show')
        $('#openAllRequests').html("Collapse Requests");
        break;
    case 2:
            $('#requests-39195611-8f6b-40de-b7a3-b0890ae57d82').addClass('collapsed')
            $('#collapse-39195611-8f6b-40de-b7a3-b0890ae57d82').addClass('collapsed')
            $('#requests-39195611-8f6b-40de-b7a3-b0890ae57d82').removeClass('show')
            $('#collapse-39195611-8f6b-40de-b7a3-b0890ae57d82').removeClass('show')
            $('#requests-6ee48502-c146-4da3-b82f-d978307eccc5').addClass('collapsed')
            $('#collapse-6ee48502-c146-4da3-b82f-d978307eccc5').addClass('collapsed')
            $('#requests-6ee48502-c146-4da3-b82f-d978307eccc5').removeClass('show')
            $('#collapse-6ee48502-c146-4da3-b82f-d978307eccc5').removeClass('show')
            $('#requests-c944e98b-5b4d-4bcf-b10e-b13dab6b891f').addClass('collapsed')
            $('#collapse-c944e98b-5b4d-4bcf-b10e-b13dab6b891f').addClass('collapsed')
            $('#requests-c944e98b-5b4d-4bcf-b10e-b13dab6b891f').removeClass('show')
            $('#collapse-c944e98b-5b4d-4bcf-b10e-b13dab6b891f').removeClass('show')
            $('#requests-19f23f22-f53f-4a0b-8f0f-38c012772a51').addClass('collapsed')
            $('#collapse-19f23f22-f53f-4a0b-8f0f-38c012772a51').addClass('collapsed')
            $('#requests-19f23f22-f53f-4a0b-8f0f-38c012772a51').removeClass('show')
            $('#collapse-19f23f22-f53f-4a0b-8f0f-38c012772a51').removeClass('show')
            $('#requests-a00c9dc5-6cf0-4c8a-9665-52645e4fea72').addClass('collapsed')
            $('#collapse-a00c9dc5-6cf0-4c8a-9665-52645e4fea72').addClass('collapsed')
            $('#requests-a00c9dc5-6cf0-4c8a-9665-52645e4fea72').removeClass('show')
            $('#collapse-a00c9dc5-6cf0-4c8a-9665-52645e4fea72').removeClass('show')
            $('#requests-3b722c97-19c8-4e4f-a755-13b24a54bc64').addClass('collapsed')
            $('#collapse-3b722c97-19c8-4e4f-a755-13b24a54bc64').addClass('collapsed')
            $('#requests-3b722c97-19c8-4e4f-a755-13b24a54bc64').removeClass('show')
            $('#collapse-3b722c97-19c8-4e4f-a755-13b24a54bc64').removeClass('show')
            $('#requests-aed24b74-a9e3-49bf-a498-ca699eb4ece5').addClass('collapsed')
            $('#collapse-aed24b74-a9e3-49bf-a498-ca699eb4ece5').addClass('collapsed')
            $('#requests-aed24b74-a9e3-49bf-a498-ca699eb4ece5').removeClass('show')
            $('#collapse-aed24b74-a9e3-49bf-a498-ca699eb4ece5').removeClass('show')
            $('#requests-70002bef-fd90-4087-9fe7-3f2c8fb58c17').addClass('collapsed')
            $('#collapse-70002bef-fd90-4087-9fe7-3f2c8fb58c17').addClass('collapsed')
            $('#requests-70002bef-fd90-4087-9fe7-3f2c8fb58c17').removeClass('show')
            $('#collapse-70002bef-fd90-4087-9fe7-3f2c8fb58c17').removeClass('show')
            $('#requests-06834e6a-2d58-44fd-a9b2-e1fe81325499').addClass('collapsed')
            $('#collapse-06834e6a-2d58-44fd-a9b2-e1fe81325499').addClass('collapsed')
            $('#requests-06834e6a-2d58-44fd-a9b2-e1fe81325499').removeClass('show')
            $('#collapse-06834e6a-2d58-44fd-a9b2-e1fe81325499').removeClass('show')
            $('#requests-c8d8247c-a1f3-4979-a236-cafd9f24c702').addClass('collapsed')
            $('#collapse-c8d8247c-a1f3-4979-a236-cafd9f24c702').addClass('collapsed')
            $('#requests-c8d8247c-a1f3-4979-a236-cafd9f24c702').removeClass('show')
            $('#collapse-c8d8247c-a1f3-4979-a236-cafd9f24c702').removeClass('show')
            $('#requests-981b34af-54f8-4c7c-898a-6cdff3294434').addClass('collapsed')
            $('#collapse-981b34af-54f8-4c7c-898a-6cdff3294434').addClass('collapsed')
            $('#requests-981b34af-54f8-4c7c-898a-6cdff3294434').removeClass('show')
            $('#collapse-981b34af-54f8-4c7c-898a-6cdff3294434').removeClass('show')
            $('#requests-a9ef9a9b-02b3-40c2-82c6-9d2edee1add1').addClass('collapsed')
            $('#collapse-a9ef9a9b-02b3-40c2-82c6-9d2edee1add1').addClass('collapsed')
            $('#requests-a9ef9a9b-02b3-40c2-82c6-9d2edee1add1').removeClass('show')
            $('#collapse-a9ef9a9b-02b3-40c2-82c6-9d2edee1add1').removeClass('show')
            $('#requests-e930847c-a100-4520-99bb-704d04c45abb').addClass('collapsed')
            $('#collapse-e930847c-a100-4520-99bb-704d04c45abb').addClass('collapsed')
            $('#requests-e930847c-a100-4520-99bb-704d04c45abb').removeClass('show')
            $('#collapse-e930847c-a100-4520-99bb-704d04c45abb').removeClass('show')
            $('#requests-b181bed5-6d99-4a35-84df-7cd129d33b4d').addClass('collapsed')
            $('#collapse-b181bed5-6d99-4a35-84df-7cd129d33b4d').addClass('collapsed')
            $('#requests-b181bed5-6d99-4a35-84df-7cd129d33b4d').removeClass('show')
            $('#collapse-b181bed5-6d99-4a35-84df-7cd129d33b4d').removeClass('show')
            $('#requests-5bd82adb-c1c7-4361-9d4f-67f234bc6ee1').addClass('collapsed')
            $('#collapse-5bd82adb-c1c7-4361-9d4f-67f234bc6ee1').addClass('collapsed')
            $('#requests-5bd82adb-c1c7-4361-9d4f-67f234bc6ee1').removeClass('show')
            $('#collapse-5bd82adb-c1c7-4361-9d4f-67f234bc6ee1').removeClass('show')
            $('#requests-ca2f42b9-cf8d-44bd-b09e-86294afec322').addClass('collapsed')
            $('#collapse-ca2f42b9-cf8d-44bd-b09e-86294afec322').addClass('collapsed')
            $('#requests-ca2f42b9-cf8d-44bd-b09e-86294afec322').removeClass('show')
            $('#collapse-ca2f42b9-cf8d-44bd-b09e-86294afec322').removeClass('show')
            $('#requests-84990463-cadd-4b69-8da7-2c23687cad7b').addClass('collapsed')
            $('#collapse-84990463-cadd-4b69-8da7-2c23687cad7b').addClass('collapsed')
            $('#requests-84990463-cadd-4b69-8da7-2c23687cad7b').removeClass('show')
            $('#collapse-84990463-cadd-4b69-8da7-2c23687cad7b').removeClass('show')
            $('#requests-58cf8178-9f7b-40e3-9e3b-63ef55bc42d5').addClass('collapsed')
            $('#collapse-58cf8178-9f7b-40e3-9e3b-63ef55bc42d5').addClass('collapsed')
            $('#requests-58cf8178-9f7b-40e3-9e3b-63ef55bc42d5').removeClass('show')
            $('#collapse-58cf8178-9f7b-40e3-9e3b-63ef55bc42d5').removeClass('show')
            $('#requests-9ad94586-de84-4544-bcfc-18fe0d3eb21b').addClass('collapsed')
            $('#collapse-9ad94586-de84-4544-bcfc-18fe0d3eb21b').addClass('collapsed')
            $('#requests-9ad94586-de84-4544-bcfc-18fe0d3eb21b').removeClass('show')
            $('#collapse-9ad94586-de84-4544-bcfc-18fe0d3eb21b').removeClass('show')
            $('#requests-d55d10be-f15c-4fe2-b3eb-9399b0728fd3').addClass('collapsed')
            $('#collapse-d55d10be-f15c-4fe2-b3eb-9399b0728fd3').addClass('collapsed')
            $('#requests-d55d10be-f15c-4fe2-b3eb-9399b0728fd3').removeClass('show')
            $('#collapse-d55d10be-f15c-4fe2-b3eb-9399b0728fd3').removeClass('show')
        $('#openAllRequests').html("Expand Requests");
        break;
}
clickCount = clickCount > 1 ? 1 : ++clickCount;
$(this).data("clickCount", clickCount)
})
</script>

<!-- Show/Hide The Skipped Tests -->

<script>
$('#openAllSkipped').on('click', function(e) {
let clickCount = $(this).data("clickCount") || 1
switch (clickCount){
    case 1:
            $('#skipped-39195611-8f6b-40de-b7a3-b0890ae57d82').removeClass('collapsed')
            $('#skipped-collapse-39195611-8f6b-40de-b7a3-b0890ae57d82').removeClass('collapsed')
            $('#skipped-39195611-8f6b-40de-b7a3-b0890ae57d82').addClass('show')
            $('#skipped-collapse-39195611-8f6b-40de-b7a3-b0890ae57d82').addClass('show')
            $('#skipped-6ee48502-c146-4da3-b82f-d978307eccc5').removeClass('collapsed')
            $('#skipped-collapse-6ee48502-c146-4da3-b82f-d978307eccc5').removeClass('collapsed')
            $('#skipped-6ee48502-c146-4da3-b82f-d978307eccc5').addClass('show')
            $('#skipped-collapse-6ee48502-c146-4da3-b82f-d978307eccc5').addClass('show')
            $('#skipped-c944e98b-5b4d-4bcf-b10e-b13dab6b891f').removeClass('collapsed')
            $('#skipped-collapse-c944e98b-5b4d-4bcf-b10e-b13dab6b891f').removeClass('collapsed')
            $('#skipped-c944e98b-5b4d-4bcf-b10e-b13dab6b891f').addClass('show')
            $('#skipped-collapse-c944e98b-5b4d-4bcf-b10e-b13dab6b891f').addClass('show')
            $('#skipped-19f23f22-f53f-4a0b-8f0f-38c012772a51').removeClass('collapsed')
            $('#skipped-collapse-19f23f22-f53f-4a0b-8f0f-38c012772a51').removeClass('collapsed')
            $('#skipped-19f23f22-f53f-4a0b-8f0f-38c012772a51').addClass('show')
            $('#skipped-collapse-19f23f22-f53f-4a0b-8f0f-38c012772a51').addClass('show')
            $('#skipped-a00c9dc5-6cf0-4c8a-9665-52645e4fea72').removeClass('collapsed')
            $('#skipped-collapse-a00c9dc5-6cf0-4c8a-9665-52645e4fea72').removeClass('collapsed')
            $('#skipped-a00c9dc5-6cf0-4c8a-9665-52645e4fea72').addClass('show')
            $('#skipped-collapse-a00c9dc5-6cf0-4c8a-9665-52645e4fea72').addClass('show')
            $('#skipped-3b722c97-19c8-4e4f-a755-13b24a54bc64').removeClass('collapsed')
            $('#skipped-collapse-3b722c97-19c8-4e4f-a755-13b24a54bc64').removeClass('collapsed')
            $('#skipped-3b722c97-19c8-4e4f-a755-13b24a54bc64').addClass('show')
            $('#skipped-collapse-3b722c97-19c8-4e4f-a755-13b24a54bc64').addClass('show')
            $('#skipped-aed24b74-a9e3-49bf-a498-ca699eb4ece5').removeClass('collapsed')
            $('#skipped-collapse-aed24b74-a9e3-49bf-a498-ca699eb4ece5').removeClass('collapsed')
            $('#skipped-aed24b74-a9e3-49bf-a498-ca699eb4ece5').addClass('show')
            $('#skipped-collapse-aed24b74-a9e3-49bf-a498-ca699eb4ece5').addClass('show')
            $('#skipped-70002bef-fd90-4087-9fe7-3f2c8fb58c17').removeClass('collapsed')
            $('#skipped-collapse-70002bef-fd90-4087-9fe7-3f2c8fb58c17').removeClass('collapsed')
            $('#skipped-70002bef-fd90-4087-9fe7-3f2c8fb58c17').addClass('show')
            $('#skipped-collapse-70002bef-fd90-4087-9fe7-3f2c8fb58c17').addClass('show')
            $('#skipped-06834e6a-2d58-44fd-a9b2-e1fe81325499').removeClass('collapsed')
            $('#skipped-collapse-06834e6a-2d58-44fd-a9b2-e1fe81325499').removeClass('collapsed')
            $('#skipped-06834e6a-2d58-44fd-a9b2-e1fe81325499').addClass('show')
            $('#skipped-collapse-06834e6a-2d58-44fd-a9b2-e1fe81325499').addClass('show')
            $('#skipped-c8d8247c-a1f3-4979-a236-cafd9f24c702').removeClass('collapsed')
            $('#skipped-collapse-c8d8247c-a1f3-4979-a236-cafd9f24c702').removeClass('collapsed')
            $('#skipped-c8d8247c-a1f3-4979-a236-cafd9f24c702').addClass('show')
            $('#skipped-collapse-c8d8247c-a1f3-4979-a236-cafd9f24c702').addClass('show')
            $('#skipped-981b34af-54f8-4c7c-898a-6cdff3294434').removeClass('collapsed')
            $('#skipped-collapse-981b34af-54f8-4c7c-898a-6cdff3294434').removeClass('collapsed')
            $('#skipped-981b34af-54f8-4c7c-898a-6cdff3294434').addClass('show')
            $('#skipped-collapse-981b34af-54f8-4c7c-898a-6cdff3294434').addClass('show')
            $('#skipped-a9ef9a9b-02b3-40c2-82c6-9d2edee1add1').removeClass('collapsed')
            $('#skipped-collapse-a9ef9a9b-02b3-40c2-82c6-9d2edee1add1').removeClass('collapsed')
            $('#skipped-a9ef9a9b-02b3-40c2-82c6-9d2edee1add1').addClass('show')
            $('#skipped-collapse-a9ef9a9b-02b3-40c2-82c6-9d2edee1add1').addClass('show')
            $('#skipped-e930847c-a100-4520-99bb-704d04c45abb').removeClass('collapsed')
            $('#skipped-collapse-e930847c-a100-4520-99bb-704d04c45abb').removeClass('collapsed')
            $('#skipped-e930847c-a100-4520-99bb-704d04c45abb').addClass('show')
            $('#skipped-collapse-e930847c-a100-4520-99bb-704d04c45abb').addClass('show')
            $('#skipped-b181bed5-6d99-4a35-84df-7cd129d33b4d').removeClass('collapsed')
            $('#skipped-collapse-b181bed5-6d99-4a35-84df-7cd129d33b4d').removeClass('collapsed')
            $('#skipped-b181bed5-6d99-4a35-84df-7cd129d33b4d').addClass('show')
            $('#skipped-collapse-b181bed5-6d99-4a35-84df-7cd129d33b4d').addClass('show')
            $('#skipped-5bd82adb-c1c7-4361-9d4f-67f234bc6ee1').removeClass('collapsed')
            $('#skipped-collapse-5bd82adb-c1c7-4361-9d4f-67f234bc6ee1').removeClass('collapsed')
            $('#skipped-5bd82adb-c1c7-4361-9d4f-67f234bc6ee1').addClass('show')
            $('#skipped-collapse-5bd82adb-c1c7-4361-9d4f-67f234bc6ee1').addClass('show')
            $('#skipped-ca2f42b9-cf8d-44bd-b09e-86294afec322').removeClass('collapsed')
            $('#skipped-collapse-ca2f42b9-cf8d-44bd-b09e-86294afec322').removeClass('collapsed')
            $('#skipped-ca2f42b9-cf8d-44bd-b09e-86294afec322').addClass('show')
            $('#skipped-collapse-ca2f42b9-cf8d-44bd-b09e-86294afec322').addClass('show')
            $('#skipped-84990463-cadd-4b69-8da7-2c23687cad7b').removeClass('collapsed')
            $('#skipped-collapse-84990463-cadd-4b69-8da7-2c23687cad7b').removeClass('collapsed')
            $('#skipped-84990463-cadd-4b69-8da7-2c23687cad7b').addClass('show')
            $('#skipped-collapse-84990463-cadd-4b69-8da7-2c23687cad7b').addClass('show')
            $('#skipped-58cf8178-9f7b-40e3-9e3b-63ef55bc42d5').removeClass('collapsed')
            $('#skipped-collapse-58cf8178-9f7b-40e3-9e3b-63ef55bc42d5').removeClass('collapsed')
            $('#skipped-58cf8178-9f7b-40e3-9e3b-63ef55bc42d5').addClass('show')
            $('#skipped-collapse-58cf8178-9f7b-40e3-9e3b-63ef55bc42d5').addClass('show')
            $('#skipped-9ad94586-de84-4544-bcfc-18fe0d3eb21b').removeClass('collapsed')
            $('#skipped-collapse-9ad94586-de84-4544-bcfc-18fe0d3eb21b').removeClass('collapsed')
            $('#skipped-9ad94586-de84-4544-bcfc-18fe0d3eb21b').addClass('show')
            $('#skipped-collapse-9ad94586-de84-4544-bcfc-18fe0d3eb21b').addClass('show')
            $('#skipped-d55d10be-f15c-4fe2-b3eb-9399b0728fd3').removeClass('collapsed')
            $('#skipped-collapse-d55d10be-f15c-4fe2-b3eb-9399b0728fd3').removeClass('collapsed')
            $('#skipped-d55d10be-f15c-4fe2-b3eb-9399b0728fd3').addClass('show')
            $('#skipped-collapse-d55d10be-f15c-4fe2-b3eb-9399b0728fd3').addClass('show')
        $('#openAllSkipped').html("Collapse All Skipped Tests");
        break;
    case 2:
            $('#skipped-39195611-8f6b-40de-b7a3-b0890ae57d82').addClass('collapsed')
            $('#skipped-collapse-39195611-8f6b-40de-b7a3-b0890ae57d82').addClass('collapsed')
            $('#skipped-39195611-8f6b-40de-b7a3-b0890ae57d82').removeClass('show')
            $('#skipped-collapse-39195611-8f6b-40de-b7a3-b0890ae57d82').removeClass('show')
            $('#skipped-6ee48502-c146-4da3-b82f-d978307eccc5').addClass('collapsed')
            $('#skipped-collapse-6ee48502-c146-4da3-b82f-d978307eccc5').addClass('collapsed')
            $('#skipped-6ee48502-c146-4da3-b82f-d978307eccc5').removeClass('show')
            $('#skipped-collapse-6ee48502-c146-4da3-b82f-d978307eccc5').removeClass('show')
            $('#skipped-c944e98b-5b4d-4bcf-b10e-b13dab6b891f').addClass('collapsed')
            $('#skipped-collapse-c944e98b-5b4d-4bcf-b10e-b13dab6b891f').addClass('collapsed')
            $('#skipped-c944e98b-5b4d-4bcf-b10e-b13dab6b891f').removeClass('show')
            $('#skipped-collapse-c944e98b-5b4d-4bcf-b10e-b13dab6b891f').removeClass('show')
            $('#skipped-19f23f22-f53f-4a0b-8f0f-38c012772a51').addClass('collapsed')
            $('#skipped-collapse-19f23f22-f53f-4a0b-8f0f-38c012772a51').addClass('collapsed')
            $('#skipped-19f23f22-f53f-4a0b-8f0f-38c012772a51').removeClass('show')
            $('#skipped-collapse-19f23f22-f53f-4a0b-8f0f-38c012772a51').removeClass('show')
            $('#skipped-a00c9dc5-6cf0-4c8a-9665-52645e4fea72').addClass('collapsed')
            $('#skipped-collapse-a00c9dc5-6cf0-4c8a-9665-52645e4fea72').addClass('collapsed')
            $('#skipped-a00c9dc5-6cf0-4c8a-9665-52645e4fea72').removeClass('show')
            $('#skipped-collapse-a00c9dc5-6cf0-4c8a-9665-52645e4fea72').removeClass('show')
            $('#skipped-3b722c97-19c8-4e4f-a755-13b24a54bc64').addClass('collapsed')
            $('#skipped-collapse-3b722c97-19c8-4e4f-a755-13b24a54bc64').addClass('collapsed')
            $('#skipped-3b722c97-19c8-4e4f-a755-13b24a54bc64').removeClass('show')
            $('#skipped-collapse-3b722c97-19c8-4e4f-a755-13b24a54bc64').removeClass('show')
            $('#skipped-aed24b74-a9e3-49bf-a498-ca699eb4ece5').addClass('collapsed')
            $('#skipped-collapse-aed24b74-a9e3-49bf-a498-ca699eb4ece5').addClass('collapsed')
            $('#skipped-aed24b74-a9e3-49bf-a498-ca699eb4ece5').removeClass('show')
            $('#skipped-collapse-aed24b74-a9e3-49bf-a498-ca699eb4ece5').removeClass('show')
            $('#skipped-70002bef-fd90-4087-9fe7-3f2c8fb58c17').addClass('collapsed')
            $('#skipped-collapse-70002bef-fd90-4087-9fe7-3f2c8fb58c17').addClass('collapsed')
            $('#skipped-70002bef-fd90-4087-9fe7-3f2c8fb58c17').removeClass('show')
            $('#skipped-collapse-70002bef-fd90-4087-9fe7-3f2c8fb58c17').removeClass('show')
            $('#skipped-06834e6a-2d58-44fd-a9b2-e1fe81325499').addClass('collapsed')
            $('#skipped-collapse-06834e6a-2d58-44fd-a9b2-e1fe81325499').addClass('collapsed')
            $('#skipped-06834e6a-2d58-44fd-a9b2-e1fe81325499').removeClass('show')
            $('#skipped-collapse-06834e6a-2d58-44fd-a9b2-e1fe81325499').removeClass('show')
            $('#skipped-c8d8247c-a1f3-4979-a236-cafd9f24c702').addClass('collapsed')
            $('#skipped-collapse-c8d8247c-a1f3-4979-a236-cafd9f24c702').addClass('collapsed')
            $('#skipped-c8d8247c-a1f3-4979-a236-cafd9f24c702').removeClass('show')
            $('#skipped-collapse-c8d8247c-a1f3-4979-a236-cafd9f24c702').removeClass('show')
            $('#skipped-981b34af-54f8-4c7c-898a-6cdff3294434').addClass('collapsed')
            $('#skipped-collapse-981b34af-54f8-4c7c-898a-6cdff3294434').addClass('collapsed')
            $('#skipped-981b34af-54f8-4c7c-898a-6cdff3294434').removeClass('show')
            $('#skipped-collapse-981b34af-54f8-4c7c-898a-6cdff3294434').removeClass('show')
            $('#skipped-a9ef9a9b-02b3-40c2-82c6-9d2edee1add1').addClass('collapsed')
            $('#skipped-collapse-a9ef9a9b-02b3-40c2-82c6-9d2edee1add1').addClass('collapsed')
            $('#skipped-a9ef9a9b-02b3-40c2-82c6-9d2edee1add1').removeClass('show')
            $('#skipped-collapse-a9ef9a9b-02b3-40c2-82c6-9d2edee1add1').removeClass('show')
            $('#skipped-e930847c-a100-4520-99bb-704d04c45abb').addClass('collapsed')
            $('#skipped-collapse-e930847c-a100-4520-99bb-704d04c45abb').addClass('collapsed')
            $('#skipped-e930847c-a100-4520-99bb-704d04c45abb').removeClass('show')
            $('#skipped-collapse-e930847c-a100-4520-99bb-704d04c45abb').removeClass('show')
            $('#skipped-b181bed5-6d99-4a35-84df-7cd129d33b4d').addClass('collapsed')
            $('#skipped-collapse-b181bed5-6d99-4a35-84df-7cd129d33b4d').addClass('collapsed')
            $('#skipped-b181bed5-6d99-4a35-84df-7cd129d33b4d').removeClass('show')
            $('#skipped-collapse-b181bed5-6d99-4a35-84df-7cd129d33b4d').removeClass('show')
            $('#skipped-5bd82adb-c1c7-4361-9d4f-67f234bc6ee1').addClass('collapsed')
            $('#skipped-collapse-5bd82adb-c1c7-4361-9d4f-67f234bc6ee1').addClass('collapsed')
            $('#skipped-5bd82adb-c1c7-4361-9d4f-67f234bc6ee1').removeClass('show')
            $('#skipped-collapse-5bd82adb-c1c7-4361-9d4f-67f234bc6ee1').removeClass('show')
            $('#skipped-ca2f42b9-cf8d-44bd-b09e-86294afec322').addClass('collapsed')
            $('#skipped-collapse-ca2f42b9-cf8d-44bd-b09e-86294afec322').addClass('collapsed')
            $('#skipped-ca2f42b9-cf8d-44bd-b09e-86294afec322').removeClass('show')
            $('#skipped-collapse-ca2f42b9-cf8d-44bd-b09e-86294afec322').removeClass('show')
            $('#skipped-84990463-cadd-4b69-8da7-2c23687cad7b').addClass('collapsed')
            $('#skipped-collapse-84990463-cadd-4b69-8da7-2c23687cad7b').addClass('collapsed')
            $('#skipped-84990463-cadd-4b69-8da7-2c23687cad7b').removeClass('show')
            $('#skipped-collapse-84990463-cadd-4b69-8da7-2c23687cad7b').removeClass('show')
            $('#skipped-58cf8178-9f7b-40e3-9e3b-63ef55bc42d5').addClass('collapsed')
            $('#skipped-collapse-58cf8178-9f7b-40e3-9e3b-63ef55bc42d5').addClass('collapsed')
            $('#skipped-58cf8178-9f7b-40e3-9e3b-63ef55bc42d5').removeClass('show')
            $('#skipped-collapse-58cf8178-9f7b-40e3-9e3b-63ef55bc42d5').removeClass('show')
            $('#skipped-9ad94586-de84-4544-bcfc-18fe0d3eb21b').addClass('collapsed')
            $('#skipped-collapse-9ad94586-de84-4544-bcfc-18fe0d3eb21b').addClass('collapsed')
            $('#skipped-9ad94586-de84-4544-bcfc-18fe0d3eb21b').removeClass('show')
            $('#skipped-collapse-9ad94586-de84-4544-bcfc-18fe0d3eb21b').removeClass('show')
            $('#skipped-d55d10be-f15c-4fe2-b3eb-9399b0728fd3').addClass('collapsed')
            $('#skipped-collapse-d55d10be-f15c-4fe2-b3eb-9399b0728fd3').addClass('collapsed')
            $('#skipped-d55d10be-f15c-4fe2-b3eb-9399b0728fd3').removeClass('show')
            $('#skipped-collapse-d55d10be-f15c-4fe2-b3eb-9399b0728fd3').removeClass('show')
        $('#openAllSkipped').html("Expand All Skipped Tests");
        break;
}
clickCount = clickCount > 1 ? 1 : ++clickCount;
$(this).data("clickCount", clickCount)
})
</script>

<!-- Show/Hide The Failures -->

<script>
$('#openAllFailed').on('click', function(e) {
let clickCount = $(this).data("clickCount") || 1
let failedItemContent
let failedItemHeading
switch (clickCount){
    case 1:
        $('#openAllFailed').html("Collapse All Failed Tests");
        break;
    case 2:
        $('#openAllFailed').html("Expand All Failed Tests");
        break;
}
clickCount = clickCount > 1 ? 1 : ++clickCount;
$(this).data("clickCount", clickCount)
})
</script>

<!-- Pretty Print the Response Body-->

<script>
function isJSON(data)
{
    var ret = true;
    try {
            JSON.parse(data);
    }catch(e) {
            ret = false;
    }
    return ret;
}

function isXML(data)
{
    return (data.length > 0 && data[0] === '<');
}

// see https://gist.github.com/sente/1083506/d2834134cd070dbcc08bf42ee27dabb746a1c54d#gistcomment-2254622
function formatXML(data) {
    const PADDING = ' '.repeat(2); // set desired indent size here
    const reg = /(>)(<)(\/*)/g;
    let pad = 0;
    xml = data.replace(reg, '$1\r\n$2$3');

    return xml.split('\r\n').map((node, index) => {
        let indent = 0;
        if (node.match(/.+<\/\w[^>]*>$/)) {
            indent = 0;
        } else if (node.match(/^<\/\w/) && pad > 0) {
            pad -= 1;
        } else if (node.match(/^<\w[^>]*[^\/]>.*$/)) {
            indent = 1;
        } else {
            indent = 0;
        }

        pad += indent;
        return PADDING.repeat(pad - indent) + node;
    }).join('\r\n');
}

$(".prettyPrint").each(function () {
        var data = $(this).text();
        // Verify whether data is JSON
        if(isJSON(data))
        {
                obj = JSON.parse(data);
                data = JSON.stringify(obj, null, 2);
        }
        else if(isXML(data)) {
            data = formatXML(data);
        }
        $(this).text(data);
});
</script>


<!-- Copy Response Body To Clipboard -->

<script>
    var clipboard = new ClipboardJS('.copyButton');

    clipboard.on('success', function(e) {
        e.clearSelection();
        $(".copyButton").addClass("bg-success text-white")
        e.trigger.textContent = '✔ Copied!';
        window.setTimeout(function() {
            $(".copyButton").removeClass("bg-success text-white")
            e.trigger.textContent = 'Copy to Clipboard';
        }, 2000);
    });
    clipboard.on('error', function(e) {
        e.clearSelection();
        $(".copyButton").addClass("bg-danger text-white")
        e.trigger.textContent = '✗ Not Copied';
        window.setTimeout(function() {
            $(".copyButton").removeClass("bg-danger text-white")
            e.trigger.textContent = 'Copy to Clipboard';
        }, 2000);
    });

</script>

<!-- Render the Description Markdown and link in the test failures -->

<script>
    const remarkable = new Remarkable();

    const descriptions = document.querySelectorAll(".renderMarkdown");
    descriptions.forEach(description => {
        description.innerHTML = renderHtmlFromMarkdown(description.textContent);
    });
    function renderHtmlFromMarkdown(markdown) {
        return remarkable.render(trim(markdown));
    }
    function trim(string) {
        return string ? string.replace(/^ +| +$/gm, "") : string;
    }
</script>

<!-- Show/Hide The Toggles When Scrolling The Page -->

<script>
window.onscroll = function() {scrollFunction()};

function scrollFunction() {
  if (document.body.scrollTop > 20 || document.documentElement.scrollTop > 20) {
    document.getElementById("topOfRequestsScreen").style.display = "block";
    document.getElementById("topOfFailuresScreen").style.display = "block";
    document.getElementById("topOfSkippedScreen").style.display = "block";
    document.getElementById("openAll").style.display = "none";
    document.getElementById("openAllRequests").style.display = "none";


  } else {
    document.getElementById("topOfRequestsScreen").style.display = "none";
    document.getElementById("topOfFailuresScreen").style.display = "none";
    document.getElementById("topOfSkippedScreen").style.display = "none";
    document.getElementById("openAll").style.display = "block";
    document.getElementById("openAllRequests").style.display = "block";

  }
}

function topFunction() {
  document.body.scrollTop = 0;
  document.documentElement.scrollTop = 0;
}
</script>

<!-- Creates The Iteration Tabs -->

<script type="text/javascript">
    "use strict";

window.onload = function () {

  // set display for all blocks of response
  var allItems = document.querySelectorAll('[class*=iteration-]');
  allItems.forEach(function(elem){
    elem.style.display = 'block';
  });

   
  let totalIterations = 5;
   

  let menu = document.querySelector('#execution-menu .nav');

  for(var i = 0; i < totalIterations; i++)
  {
    let li = document.createElement('li');
    li.appendChild(document.createTextNode((i + 1)));
    li.setAttribute('id', 'iteration-' + i);
    li.classList.add("custom-tab");
    li.classList.add("itPassed");

    li.addEventListener('click', function() {
      //set display to none for all except row
      let allItems = document.querySelectorAll('[class*=iteration-]:not(.row)');
      allItems.forEach(function(elem) {
        elem.style.display = 'none';
      })

      let allMenus = document.querySelectorAll('[id*=iteration-]');
      allMenus.forEach(function(elem){
        elem.style.borderBottom = 'none';
      })

      this.style.borderBottom = 'solid 3px #032a33';

      let items = document.querySelectorAll("." + this.id + ':not(.row)');
      items.forEach(function(elem) {
        elem.style.display = elem.style.display == 'block' ? 'none' : 'block';
      })
    });
    menu.appendChild(li);
  }

  //shows first tab data
  document.getElementById('iteration-0').click();
  document.getElementById('iterationSelected').innerHTML = `Iteration ${document.getElementById('iteration-0').innerHTML} selected`

}
</script>

<!-- Create the Selected Iteration Label -->

<script>
$(document).ready(function(){
    $(function() {
        $("#iterationList li").click(function() {
            document.getElementById('iterationSelected').innerHTML = "Iteration " + this.innerHTML + " selected"
        });
    });
});
</script>

<!-- Filter Action for the Iterations -->

<script>
$("#filterInput").on("input paste", function() {
    var value = $(this).val();
    $("#iterationList li").filter(function() {
	    $("#showOnlyFailures").data("clickCount") ? $("#showOnlyFailures").click():null;
        $(this).toggle($(this).text().indexOf(value) > -1)
    });
});
</script>

<!-- Showing the Failed Interations -->

<script>
$('#showOnlyFailures').on('click', function(e) {
    let clickCount = $(this).data("clickCount") || 1
	$("#filterInput").val()!="" && clickCount==1 ? $("#filterInput").val('').trigger('input'): null;
    let selectedIteration = $('#iterationList li').filter(function () {
        return $(this).css('border-bottom').indexOf("solid") > -1 && $(this).hasClass('itFailed');
    });
    selectedIteration.length || clickCount > 1 ? null : $("#iterationList li.itFailed")[0].click()
    $("#iterationList li.itPassed").toggle()
    $("div.bg-success [id*=requests]").parents('[class^="row iteration-"]').toggle();
    clickCount = clickCount > 1 ? 1 : ++clickCount;
    clickCount > 1 ? $("#showOnlyFailures").html("Show All Iterations") : $("#showOnlyFailures").html("Show Failed Iterations");
    $(this).data("clickCount", clickCount)
})
</script>
</body>
</html>



