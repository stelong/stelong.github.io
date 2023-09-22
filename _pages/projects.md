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

        .description a {
            color: #007bff; /* Set the default link color to blue (or your desired color) */
            text-decoration: none; /* Remove underlines from links */
            transition: color 0.2s; /* Add a smooth color transition on hover */
        }

        .description a:hover {
            color: #0056b3; /* Change the link color when hovering (you can adjust the color as needed) */
            text-decoration: underline; /* Add underlines when hovering */
        }

        table.page-list {
            width: 100%;
            border-collapse: collapse; /* Make table borders invisible */
        }

        .row {
            display: flex;
            flex-wrap: wrap;
            margin: 0 -10px;
        }

        .clickable-row {
            cursor: pointer;
            <!-- display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 10px;
            border-bottom: 1px solid #ddd; -->
        }

        .clickable-row:hover {
            background-color: #f0f0f0;
        }

        <!-- .description {
            flex-grow: 1;
            padding-right: 20px;
        } -->

        .description strong {
            margin: 0;
            text-align: left; /* Left-align the heading */
        }

        .description p {
            margin: 0;
            text-align: left; /* Left-align the heading */
        }

        .logo {
            width: 50px;
            height: 50px;
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
                        <strong><a href="/projects/GPErks"> GPErks </a></strong>
                        <p>
                        A Python library to (bene)fit Gaussian Process Emulators.
                        </p>
                    </td>
                    <td>
                        <img class="logo" src="/images/GPErks_logo.png">
                    </td>
                </tr>
                <tr class="clickable-row" data-href="/projects/TheFlysLoop">
                    <td class="description">
                        <strong><a href="/projects/TheFlysLoop"> The Fly's Loop </a></strong>
                        <p>
                        Unravelling the chaotic behavior of a nervous fly at lunchtime.
                        </p>
                    </td>
                    <td>
                        <img class="logo" src="/images/TheFlysLoop_logo.png">
                    </td>
                </tr>
            </table>
        </div>
    </div>
</body>
</html>
