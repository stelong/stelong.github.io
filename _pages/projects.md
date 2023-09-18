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

        .square-cell {
            width: 50px;
            height: 50px;
            vertical-align: top; /* Align image to the top of the cell */
        }

        .description-cell {
            /* Adjust the width of the first column cell as needed */
        }

        .logo-cell {
            text-align: center; /* Center the content horizontally */
            padding: 0; /* Remove padding */
        }

        .logo-img {
            max-width: 80%; /* Make the image occupy the whole cell width */
            max-height: 80%; /* Make the image occupy the whole cell height */
            display: block; /* Remove any potential extra spacing */
            margin: 0 auto; /* Center the image horizontally */
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
                        <td class="description-cell">GPErks</td>
                        <td class="logo-cell">
                            <img class="logo-img" src="/images/GPErks_logo.png" alt="GPErks_logo">
                        </td>
                    </tr>
                    <tr class="clickable-row" data-href="/projects/TheFlysLoop">
                        <td class="description-cell">The Fly's Loop</td>
                        <td class="logo-cell">
                            <img class="logo-img" src="/images/TheFlysLoop_logo.png" alt="TheFlysLoop_logo">
                        </td>
                    </tr>
                    <tr class="clickable-row" data-href="/projects/ExampleProject">
                        <td class="description-cell">Progetto 3</td>
                        <td class="logo-cell">
                            <div class="square-figure" style="background-color: #00ff00;"></div>
                        </td>
                    </tr>
                </table>
            </div>
        </div>
    </div>
</body>
</html>
