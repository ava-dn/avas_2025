{
 "cells": [
  {
   "cell_type": "code",
   "execution_count": null,
   "metadata": {
    "vscode": {
     "languageId": "html"
    }
   },
   "outputs": [],
   "source": [
    "<html lang=\"en\">\n",
    "<head>\n",
    "    <meta charset=\"UTF-8\">\n",
    "    <meta name=\"viewport\" content=\"width=device-width, initial-scale=1.0\">\n",
    "    <style>\n",
    "body {\n",
    "font-family: Arial, sans-serif;\n",
    "display: flex;\n",
    "flex-direction: column;\n",
    "align-items: center;\n",
    "justify-content: center;\n",
    "height: 100vh;\n",
    "background-color: #f0f0f0;\n",
    "}\n",
    "#cookie {\n",
    "width: 250px; /* Increase the cookie size */\n",
    "cursor: pointer;\n",
    "margin-bottom: 20px;\n",
    "}\n",
    "#score {\n",
    "font-size: 32px; /* Increase score text size */\n",
    "color: white;\n",
    "}\n",
    ".game-container {\n",
    "background-color: #333; /* Add a background color */\n",
    "padding: 30px; /* Increase padding for a bigger box */\n",
    "border-radius: 10px; /* Rounded corners for a smoother look */\n",
    "width: 350px; /* Increase container width */\n",
    "text-align: center;\n",
    "}\n",
    "</style>\n",
    "\n",
    "</head>\n",
    "<body>\n",
    "    <h1>Cookie Clicker</h1>\n",
    "    <img src=\"{{ site.baseurl }}/images/cookie.png\" alt=\"Cookie\" id=\"cookie\">\n",
    "    <div id=\"score\">Score: 0</div>\n",
    "    <audio id=\"clickSound\" src=\"{{ site.baseurl }}/assets/click.wav\"></audio>\n",
    "    <script>\n",
    "        let score = 0;\n",
    "        const cookie = document.getElementById('cookie');\n",
    "        const scoreDisplay = document.getElementById('score');\n",
    "        const clickSound = document.getElementById('clickSound');\n",
    "        cookie.addEventListener('click', function() {\n",
    "            score++;\n",
    "            scoreDisplay.textContent = 'Score: ' + score;\n",
    "            clickSound.play();\n",
    "        });\n",
    "    </script>\n",
    "</body>\n",
    "</html>"
   ]
  }
 ],
 "metadata": {
  "kernelspec": {
   "display_name": "venv",
   "language": "python",
   "name": "python3"
  },
  "language_info": {
   "codemirror_mode": {
    "name": "ipython",
    "version": 3
   },
   "file_extension": ".py",
   "mimetype": "text/x-python",
   "name": "python",
   "nbconvert_exporter": "python",
   "pygments_lexer": "ipython3",
   "version": "3.12.3"
  }
 },
 "nbformat": 4,
 "nbformat_minor": 2
}

