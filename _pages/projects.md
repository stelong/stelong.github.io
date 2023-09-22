---
layout: page
title: Projects
permalink: /projects/
---

<html>
<head>
    <style>
        body, html {
            margin: 0;
            padding: 0;
        }

        table.page-list {
            width: 100%;
        }

        tr.clickable-row {
            cursor: pointer;
        }

        .text-cell {
            vertical-align: top; /* Align text to the top */
        }

        .logo-cell {
            width: 30px; /* Set fixed width for the second column (adjust as needed) */
            height: 30px; /* Set fixed height for the second column (same as width for a square) */
            text-align: center; /* Center the content horizontally */
            padding: 0; /* Remove padding */
        }

        .logo-img {
            width: 100%; /* Make the image occupy the whole cell width */
            height: 100%; /* Make the image occupy the entire cell height */
            display: block; /* Remove any potential extra spacing */
            border: 0; /* Remove any borders */
        }
    </style>
    <script src="https://code.jquery.com/jquery-3.6.0.min.js"></script>
    <script>
        $(document).ready(function() {
            $(".clickable-row").click(function() {
                window.location = $(this).data("href");
            });
        });
    </script>
</head>
<body>
    <div id="main" role="main">
        <div class="full">
            <div class="row">
                <table class="page-list">
                    <tr class="clickable-row" data-href="/projects/GPErks">
                        <td class="text-cell">
                            <strong>GPErks</strong><br>
                            A Python library to (bene)fit Gaussian Process Emulators
                        </td>
                        <td class="logo-cell">
                            <img class="logo-img" src="/images/GPErks_logo.png" alt="GPErks_logo">
                        </td>
                    </tr>
                    <tr class="clickable-row" data-href="/projects/TheFlysLoop">
                        <td class="text-cell">
                            <strong>The Fly's Loop</strong><br>
                            Unravelling the chaotic behavior of a nervous fly at lunchtime
                        </td>
                        <td class="logo-cell">
                            <img class="logo-img" src="/images/TheFlysLoop_logo.png" alt="TheFlysLoop_logo">
                        </td>
                    </tr>
                </table>
            </div>
        </div>
    </div>
</body>
</html>
