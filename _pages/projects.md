---
layout: page
title: Projects
permalink: /projects/
---

In this section, you can find some of the projects I've worked on in my spare time. Some of these started off as addressing a real research need and ended up becoming useful tools, while others were just for fun.

<html>
<head>
    <style>

        .page-list {
            width: 100%;
            display: flex;
        }

        .row {
            display: flex;
            align-self: stretch;
        }

        .clickable-row {
            cursor: pointer;
            display: flex;
            justify-content: space-between;
            align-items: center;
            background-color: #ffffff;
            border-top: none;
            border-bottom: 1px solid #ccc;
        }

        .clickable-row:hover {
            background-color: #f0f0f0;
        }

        .column1 {
            flex: 7;
            border: none;
        }

        .column1 a {
            color: #404040;
            transition: color 0.2s;
        }

        .column1 a:hover {
            color: #4183C4;
        }

        .column1 p {
            margin: 0;
        }

        .column2 {
            flex: 1;
            display: flex;
            justify-content: center;
            align-items: center;
            position: relative;
            border: none;
            height: 100%;
        }

        .column2::before {
            content: "";
            padding-top: 100%;
            width: 0;
            height: 0;
        }

        .column2 img {
            max-width: 100%;
            max-height: 100%;
            object-fit: cover;
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
                    <td class="column1">
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
                    <td class="column1">
                        <strong><a href="/projects/TheFlysLoop"> The Fly's Loop </a></strong>
                        <p>
                        Unravelling the chaotic behavior of a nervous fly at lunchtime.
                        </p>
                    </td>
                    <td class="column2">
                        <img class="logo" src="/images/TheFlysLoop_logo.png">
                    </td>
                </tr>
                <tr class="clickable-row" data-href="/projects/MultiChannel">
                    <td class="column1">
                        <strong><a href="/projects/MultiChannel"> Multi-Channel Images </a></strong>
                        <p>
                        Tricks for handling multi-channel images (n > 4) in fastai.
                        </p>
                    </td>
                    <td class="column2">
                        <img class="logo" src="/images/MultiChannel_logo.png">
                    </td>
                </tr>
            </table>
        </div>
    </div>
</body>
</html>

