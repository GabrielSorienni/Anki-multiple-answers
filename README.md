This code allows the inputting of one of multiple answers in an Anki card's type field, so long as each answer can be separated with a consistent string of characters. Does not require add-ons.
Demonstrated in [this video](https://www.youtube.com/watch?v=sKlobvbJdYc).

This is a modification of [Input correct-incorrect](https://gist.github.com/hinekidori/4085a1222af572057f1058d43cfce773) by hinekidori (as provided in [this video](https://www.youtube.com/watch?v=cNOCMtZj8t0)) to extend its functionality.

# How to use
* Copy-and-paste the contents of [back-template.html](back-template.html) into the card's back template.
* Place the field containing the correct answer inside the div at the top of the pasted code.
* Towards the bottom of the code, find the line starting with ``var answerArray`` and modify the string inside ``answerFull.split("")`` to the preferred answer separator.
  * The default separator is ``; ``, meaning each answer must be separated with a semicolon, followed by a space.
* Style ``div#correct`` and ``div#incorrect`` and modify the lines starting with ``typeans.innerHTML`` to change how the answer is presented.

# Notes
* The answer verification is case-insensitive by default, meaning strings like "answer" and "aNswer" are equivalent.
  * This can be remedied by removing the call to ``map`` in the declaration of ``answerArray`` and the call to ``toLowerCase`` in the answer verification to make it case-sensitive.
* The input is treated to remove Anki's "filler dashes" when an answer is insufficiently long, meaning answers starting or ending with ``-`` will not be properly verified, and would require additional code in order to function.
* As per usual, type fields do not influence scheduling of cards.
