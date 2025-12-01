Site can genrate a random password that can include or exclude uppercase letters, numbers and symbols. 
Working link: https://samirulu87-jpg.github.io/Js-Password-generator/

notes



          Script 
          //Define varables 
      const genbtn= document.getElementById("generate")
      const lengthInput = document.getElementById("length"); 

      
      genbtn.addEventListener("click", () => {
        const lengthValue = Number(lengthInput.value);
      
      
      let result = generateRandomLetters(lengthValue);
      
      
          if (document.querySelector('#Uppercase').checked) {
          result = applyUppercase(result);
        }
        
        if (document.querySelector('#numbers').checked) {
           result = applyNumbers(result);
        }
        
        if (document.querySelector('#symbols').checked) {
          result = applySymbols(result);
        }
      
       document.getElementById("password").value = result;
      
      }) 
      
      //Uppercase replace function
      function applyUppercase(str) {
        const chars = str.split(""); 
        for (let i = 0; i < chars.length; i++) {
          if (Math.random() < 0.5) {
            chars[i] = chars[i].toUpperCase();
          }
        }
        return chars.join(""); 
      };
      
      //Number replace function
      function applyNumbers(str) {
        const chars = str.split("");
        for (let i = 0; i < chars.length; i++) {
          if (Math.random() < 0.3) { 
            chars[i] = Math.floor(Math.random() * 10).toString();
          }
        }
        return chars.join("");
      }
      
      //Letter length generator 
       function generateRandomLetters(length) {
        const letters = "abcdefghijklmnopqrstuvwxyz";
        let result = "";
      
        for (let i = 0; i < length; i++) {
          let randomIndex = Math.floor(Math.random() * letters.length);
          result += letters[randomIndex];
        }
       
         return result;
      };
      
      //Symbol replace generator 
      function applySymbols(str) {
        const chars = str.split("");
        const symbols = "!@#$%^&*()_+-={}[]<>?/|~";
      
        for (let i = 0; i < chars.length; i++) {
          if (Math.random() < 0.3) {  
            const r = Math.floor(Math.random() * symbols.length);
            chars[i] = symbols[r];
          }
        }
      
        return chars.join("");
      };



