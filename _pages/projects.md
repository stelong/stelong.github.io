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
            border-collapse: collapse; /* Make table borders invisible */
        }

        tr.clickable-row {
            cursor: pointer;
        }

        td.description {
            vertical-align: top; /* Align text to the top */
        }

        td img {
            max-width: 100%; /* Make the image fit within the cell */
            height: auto; /* Preserve aspect ratio */
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
    <div class="full">
        <div class="row">
            <table class="page-list">
                <tr class="clickable-row" data-href="/projects/GPErks">
                    <td class="description">
                        <h2><a href="/projects/GPErks"> GPErks </a></h2>
                        <p>
                        A Python library to (bene)fit Gaussian Process Emulators.
                        </p>
                    </td>
                    <td>
                        <img src="/images/GPErks_logo.png" width="30" height="30">
                    </td>
                </tr>
                <tr class="clickable-row" data-href="/projects/GPErks">
                    <td class="description">
                        <h2><a href="/projects/TheFlysLoop"> The Fly's Loop </a></h2>
                        <p>
                        Unravelling the chaotic behavior of a nervous fly at lunchtime.
                        </p>
                    </td>
                    <td>
                        <img src="/images/TheFlysLoop_logo.png" width="30" height="30">
                    </td>
                </tr>
            </table>
        </div>
    </div>
</body>
</html>
