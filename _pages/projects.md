---
layout: page
title: Projects
permalink: /projects/
---

<html>
<head>
    <style>

        .page-list {
            width: 100%;
            display: flex;
        }

        .row {
            display: flex;
        }

        .clickable-row {
            cursor: pointer;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .clickable-row:hover {
            background-color: #f0f0f0;
        }

        .description {
            flex: 7;
            border: none;
        }

        .description a {
            color: #4183C4;
            transition: color 0.2s;
        }

        .description a:hover {
            color: #193450;
        }

        .description p {
            margin: 0;
        }

        .column2 {
            flex: 1;
            border: none;
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
                    <td class="column2">
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
                    <td class="column2">
                        <img class="logo" src="/images/TheFlysLoop_logo.png">
                    </td>
                </tr>
            </table>
        </div>
    </div>




</body>
</html>
