<!DOCTYPE html> <html lang="en"> <head> <meta charset="UTF-8" /> <meta name="viewport" content="width=device-width, initial-scale=1.0" /> <meta http-equiv="X-UA-Compatible" content="ie=edge" /> <link rel="stylesheet" href="style.css" /> <title> Угадай моё число!</title> </head> <body> <header> <h1> Угадай моё число!</h1>

  <section class="range-input">
    <label for="minNumber"> Минимальное число:</label>
    <input type="range" id="minNumber" min="1" max="100" value="1" />
  </section>
  
  <section class="range-input">
    <label for="maxNumber"> Максимальное число :</label>
    <input type="range" id="maxNumber" min="1" max="100" value="100" />
  </section>
  </button>
  <button class="btn-guess">Загадать</button> 
  <div class="number">?</div>
</header>
<main>
  <section class="left">
    <input type="number" class="guess" />
    <button class="btn check">Проверь!</button>
  </section>
  <section class="right">
    <p class="message"> Начнём угадывать...</p>
    <p class="label-score">💯 С чёт: <span class="score">0</span></p>
    <p class="label-highscore">
      🥇 Рекорд: <span class="highscore">0</span>
    </p>
  </section>
</main>
<script src="script.js"></script>
</body> </html>. 'use strict'; document.querySelector('.btn-guess').addEventListener('click', () => { });

const minNumber = Number(document.getElementById('minNumber').value); const maxNumber = Number(document.getElementById('maxNumber').value);

const guessedNumber = Math.floor(Math.random() * (maxNumber - minNumber + 1)) + minNumber;

const displayMessage = function (message) { document.querySelector('.message').textContent = message; };

document.querySelector('.number').textContent = guessedNumber;

document.querySelector('.btn-guess').addEventListener('click', () => { const minNumber = Number(document.getElementById('minNumber').value); const maxNumber = Number(document.getElementById('maxNumber').value);

const guessedNumber = Math.floor(Math.random() * (maxNumber - minNumber + 1)) + minNumber;

document.querySelector('.number').textContent = guessedNumber;

});

document.querySelector('.check').addEventListener('click', () => { const guess = Number(document.querySelector('.guess').value); console.log(guess, typeof guess);

if (!guess) { displayMessage('⛔️ Нету цифры!'); } else { makeGuess(guess); } });

const RANGE_FACTOR_LOW = 5; const RANGE_FACTOR_HIGH = 10; const minRange = guessedNumber / RANGE_FACTOR_LOW; const maxRange = guessedNumber * RANGE_FACTOR_HIGH;

const makeGuess = function(guess) { if (!isNumberInRange(guess, minRange, maxRange)) { displayMessage('⛔️ Цифры нижеуказанного!'); } else if (guess === guessedNumber) { displayMessage('🎉 Правильно!'); } else if (guess < guessedNumber) { if (guess >= minRange * RANGE_FACTOR_LOW) { displayMessage('📉 Очень низко!'); } else if (guess >= minRange) { displayMessage('📉 Немного ниже!'); } } else { if (guess <= maxRange * RANGE_FACTOR_HIGH) { displayMessage('📈 Очень высоко!'); } else if (guess <= maxRange) { displayMessage('📈 Немного выше!'); } } };

const minNumberInput = document.getElementById("minNumber"); const maxNumberInput = document.getElementById("maxNumber"); const minNumberLabel = document.querySelector("label[for='minNumber']"); const maxNumberLabel = document.querySelector("label[for='maxNumber']");

minNumberInput.addEventListener("input", function() { minNumberLabel.textContent = "Минимальное число: " + minNumberInput.value; });

maxNumberInput.addEventListener("input", function() { maxNumberLabel.textContent = "Максимальное число: " + maxNumberInput.value; });

document.querySelector('.check').addEventListener('click', () => { const guess = Number(document.querySelector('.guess').value); console.log(guess, typeof guess);

if (!guess) { displayMessage('⛔️ Этот номер не указaн !'); } else if (!isNumberInRange(guess, Number(minNumberInput.value), Number(maxNumberInput.value))) { displayMessage('⛔️ Это число ниже указенного'); } else if (guess === secretNumber) { } else if (guess !== secretNumber) {

} }); Add a function that will hide the hidden number that is in <div class="number">?</div>
