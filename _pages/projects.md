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

        .square-figure {
            width: 50px;
            height: 50px;
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
                    <tr class="clickable-row" data-href="/_projects/GPErks">
                        <td class="description">Progetto 1</td>
                        <td>
                            <div class="square-figure" style="background-color: #000;"></div>
                        </td>
                    </tr>
                    <tr class="clickable-row" data-href="/_projects/TheFlysLoop">
                        <td class="description">Progetto 2</td>
                        <td>
                            <div class="square-figure" style="background-color: #ff0000;"></div>
                        </td>
                    </tr>
                    <tr class="clickable-row" data-href="/_projects/ExampleProject">
                        <td class="description">Progetto 3</td>
                        <td>
                            <div class="square-figure" style="background-color: #00ff00;"></div>
                        </td>
                    </tr>
                </table>
            </div>
        </div>
    </div>
</body>
</html>
