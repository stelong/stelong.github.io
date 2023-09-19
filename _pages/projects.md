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

        .image-cell {
            flex: 0 0 auto; /* Set a fixed width for the image cell */
            height: 100%; /* Make the image cell occupy the full row height */
            margin: 0; /* Remove margin for image cell */
            padding: 0; /* Remove padding for image cell */
        }

        .text-cell {
            flex: 1; /* Make the text cell occupy remaining space */
        }

        .image-bg {
            width: 100%; /* Set the image background width to 100% of the cell */
            height: 100%; /* Set the image background height to 100% of the cell */
            background-repeat: no-repeat; /* Prevent image repetition */
            background-size: cover; /* Cover the entire cell with the image */
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
                            <div class="image-cell image-bg" style="background-image: url('/images/GPErks_logo.png');"></div>
                            <div class="text-cell">
                                <p>GPErks</p>
                                <p>A Python library to (bene)fit Gaussian Process Emulators</p>
                            </div>
                        </td>
                    </tr>
                    <!-- Add similar rows for other projects, changing the image path -->
                    <tr class="clickable-row" data-href="/projects/TheFlysLoop">
                        <td class="row-content">
                            <div class="image-cell image-bg" style="background-image: url('/images/TheFlysLoop_logo.png');"></div>
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
