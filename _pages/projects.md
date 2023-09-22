---
layout: page
title: Projects
permalink: /projects/
---

<html>
    <head>
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
                            <img src="/images/GPErks_logo.png">
                        </td>
                    </tr>
                    <tr class="clickable-row" data-href="/projects/GPErks">
                        <td class="description">
                            <h2><a href="/projects/GPErks"> The Fly's Loop </a></h2>
                            <p>
                            Unravelling the chaotic behavior of a nervous fly at lunchtime.
                            </p>
                        </td>
                        <td>
                            <img src="/images/TheFlysLoop_logo.png">
                        </td>
                    </tr>
                </table>
            </div>
        </div>
    </body>
</html>
