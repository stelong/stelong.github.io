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

        .row-content {
            display: flex;
            align-items: center;
            height: 100%; /* Make the row occupy the full height */
        }

        .square-cell {
            flex: 0 0 50px; /* Set a fixed width for the square */
            height: 100%; /* Make the square occupy the full row height */
            background-image: url("/images/GPErks_logo.png"); /* Set the image as background */
            background-size: cover; /* Cover the entire cell with the image */
        }

        .text-cell {
            /* Adjust the width of the text cell as needed */
        }

        .logo-img {
            max-width: 100%; /* Make the image occupy the whole cell width */
            max-height: 100%; /* Make the image occupy the whole cell height */
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
                        <td class="row-content">
                            <div class="square-cell"></div>
                            <div class="text-cell">
                                <p>GPErks</p>
                                <p>A Python library to (bene)fit Gaussian Process Emulators</p>
                            </div>
                        </td>
                    </tr>
                    <!-- Add similar rows for other projects, changing the image path -->
                    <tr class="clickable-row" data-href="/projects/TheFlysLoop">
                        <td class="row-content">
                            <div class="square-cell" style="background-image: url('/images/TheFlysLoop_logo.png');"></div>
                            <div class="text-cell">
                                <p>The Fly's Loop</p>
                                <p>Unravelling the chaotic behaviour of a nervous fly at lunch time</p>
                            </div>
                        </td>
                    </tr>
                </table>
            </div>
        </div>
    </div>
</body>
</html>
