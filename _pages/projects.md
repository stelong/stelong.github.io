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
                        <td class="description-cell">
                            <div>
                                <strong>GPErks</strong><br>
                                A Python library to (bene)fit Gaussian Process Emulators
                            </div>
                        </td>
                        <td class="logo-cell">
                            <img class="logo-img" src="/images/GPErks_logo.png" alt="GPErks_logo">
                        </td>
                    </tr>
                    <tr class="clickable-row" data-href="/projects/TheFlysLoop">
                        <td class="description-cell">
                            <div>
                                <strong>The Fly's Loop</strong><br>
                                Unravelling the chaotic behaviour of a nervous fly at lunch time
                            </div>
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
