function checkNumber() {
    const number = parseInt(document.getElementById('number').value);
    let result = "";

    if (number < 0 || number > 36) {
        result = "Please enter a valid number between 0 and 36.";
    } else {
        // Column Calculation
        let column = (number % 3 === 1) ? "First" : (number % 3 === 2) ? "Second" : "Third";

        // Dozen Calculation
        let dozen = (number >= 1 && number <= 12) ? "First" :
                    (number >= 13 && number <= 24) ? "Second" : "Third";

        // Even or Odd
        let evenOdd = (number === 0) ? "None" : (number % 2 === 0) ? "Even" : "Odd";

        // Red or Black
        const redNumbers = [1, 3, 5, 7, 9, 12, 14, 16, 18, 19, 21, 23, 25, 27, 30, 32, 34, 36];
        let color = (redNumbers.includes(number)) ? "Red" : "Black";

        // Big or Small
        let size = (number >= 1 && number <= 18) ? "Small" : "Big";

        result = `Number: ${number}<br>
                  Column: ${column}<br>
                  Dozen: ${dozen}<br>
                  Even/Odd: ${evenOdd}<br>
                  Color: ${color}<br>
                  Size: ${size}`;
    }

    document.getElementById('result').innerHTML = result;
}
