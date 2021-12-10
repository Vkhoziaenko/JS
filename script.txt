function CalcTask1() {
  let x = document.getElementById('task_1_input').value;

  let result = (Math.pow(x, 2) - 7 * x + 10) / (Math.pow(x, 2) - 8 * x + 12)
  document.getElementById('task_1_output').value = "The result is " + result.toString();
}


function CalcTask2() {
  let x = parseFloat(document.getElementById('task_2_input_1').value);
  let y = parseFloat(document.getElementById('task_2_input_2').value);
  let z = parseFloat(document.getElementById('task_2_input_3').value);

  let output_string = "";
  let sum = x + y + z;
  output_string += "Сумма: " + sum.toString() + "\n";

  if (x < y && x < z)
    output_string += "Первая самая лёгкая. Вес: " + x.toString();
  else if (y < x && y < z)
    output_string += "Вторая самая лёгкая. Вес: " + y.toString();
  else if (z < x && z < y)
    output_string += "Третья самая лёгкая. Вес: " + z.toString();

  output_string += "\n";

  if (x > y && x > z)
    output_string += "Первая самая тяжёлая. Вес: " + x.toString();    
  if (y > x && y > z)
    output_string += "Вторая самая тяжёлая. Вес: " + y.toString();
  else if (z > x && z > y)
    output_string += "Третья самая тяжёлая. Вес: " + z.toString();

  document.getElementById('task_2_output').value = output_string;
}


function CalcTask3() {
  let lastname = document.getElementById('task_3_input').value;
  let vowels = "aeiouy";
  let vowels_ctr = 0;

  for (i = 0; i < lastname.length; ++i) {
   if (vowels.includes(lastname.charAt(i))) {
     vowels_ctr++;
   }
  }

  let output_string = vowels_ctr.toString() + " гласных. "
  + (lastname.length - vowels_ctr) + " согласных."
  document.getElementById('task_3_output').value = output_string; 
}


function CalcTask4() {
  let input_string = document.getElementById('task_4_input').value;
  let output_string = "";

  if (input_string.length < 20) {
    output_string = "Короткая строка. Необходимо 20 символов.";
    document.getElementById('task_4_output').value = output_string;     
    return null;
  }

  let symbol = input_string.charAt(4);
  let ctr = 0;
  for (i = 0; i < input_string.length; ++i)
    if (input_string.charAt(i) === symbol) ctr++;

  output_string = "Символ " + symbol + " встречается " + ctr + " раз.";
  document.getElementById('task_4_output').value = output_string;       
}


function CalcTask5() {
  let x = parseFloat(document.getElementById('task_5_input_1').value);
  let y = parseFloat(document.getElementById('task_5_input_2').value);
  let action = parseInt(document.getElementById('task_5_input_3').value);
  let output_string = '';

  if (y === 0.0 && action == 4) {
    output_string = "Деление на ноль не определено!";
    document.getElementById('task_5_output').value = output_string;
    return null;    
  }

  switch (action) {
    case 1:
      output_string = x.toString() + " + " + y.toString() + " = " + (x + y).toString();
      break;
    case 2:
      output_string = x.toString() + " - " + y.toString() + " = " + (x - y).toString();
      break;
    case 3:
        output_string = x.toString() + " * " + y.toString() + " = " + (x * y).toString();
      break;
    case 4:
        output_string = x.toString() + " / " + y.toString() + " = " + (x / y).toString();
      break;
    default:
      output_string = "Неверное арифметическое действие!";
  }

  document.getElementById('task_5_output').value = output_string;       
}


function CalcTask6() {
  let I = parseFloat(document.getElementById('task_6_input_1').value);
  let U = parseFloat(document.getElementById('task_6_input_2').value);
  output_string = "";

  if (I === 0.0) {
    output_string = "Деление на ноль не определено!";
    document.getElementById('task_6_output').value = output_string;
    return null; 
  }

  let R = U / I
  output_string = "R = U / I. Сопротивление равно: " + R.toString();
  document.getElementById('task_6_output').value = output_string;
}


function CalcTask7() {
  let R1 = parseFloat(document.getElementById('task_7_input_1').value);
  let R2 = parseFloat(document.getElementById('task_7_input_2').value);
  output_string = "";

  let R = R1 + R2;
  output_string = "При последовательном соединении R = R1 + R2 = " + R.toString() + ". ";

  if (R1 === 0.0 && R2 === 0.0) {
    output_string += "Деление на ноль не определено!";
    document.getElementById('task_7_output').value = output_string;
    return null; 
  }

  R = (R1 * R2) / (R1 + R2);
  output_string += "При последовательном соединении R = (R1 * R2) / (R1 + R2) = "
  + R.toString() + ". ";
  document.getElementById('task_7_output').value = output_string;
}


function CalcTask8() {
  input_str = document.getElementById('task_8_input').value;
  symb_arr = input_str.split('');		
  a_ctr = false;
  
  for (i = 0; i < input_str.length; ++i) {
    if (symb_arr[i] == 'a' && (!a_ctr)) {
      symb_arr[i] = 'o';
      a_ctr = true;
    } 
    else if (symb_arr[i] == 'a' && a_ctr) {
      symb_arr.splice(i, 1);
    }
    else if (symb_arr[i] === ' ') {
      a_ctr = false;
    }
  }

  output_string = symb_arr.join('');
  document.getElementById('task_8_output').value = output_string;
}


function CalcTask9() {
  let output_string = "Время ";
  let date_obj = new Date();
  let hours = date_obj.getHours();
  let minutes = date_obj.getMinutes();

  if ((hours == 7 && minutes >= 0 && minutes <= 59) || (hours == 8 && minutes == 0))
    output_string += "завтрака";
  else if ((hours == 13 && minutes >= 0 && minutes <= 59) || (hours == 14 && minutes == 0))
    output_string += "обеда";
  else if ((hours == 19 && minutes >= 0 && minutes <= 59) || (hours <= 20 && minutes == 0))
    output_string += "ужина";
  else if ((hours >= 9 && hours <= 17) || (hours == 18 && minutes == 0))
    output_string += "работы";
  else if ((hours >= 18 && hours <= 22) || (hours == 23 && minutes == 0))
    output_string += "отдыха";
  else if ((hours == 23 && minutes >= 0 && minutes <= 59) || (hours >= 0 && hours <= 5) || (hours == 6 && minutes >= 0 && minutes <= 30))
    output_string += "сна";

  if (output_string.length == 6)
    output_string += "неизветсно";
  document.getElementById('task_9_output').value = output_string;
}


function CalcTask10() {
  let output_string = '';

  nextPrime:
    for (i = 2; i <= 10; ++i) {

      for (j = 2; j < i; ++j) {
        if (i % j ==0) continue nextPrime;
      }

      output_string += (i + ' ');
    }

    document.getElementById('task_10_output').value = output_string;
}


function CalcTask11() {
  let input_string = document.getElementById('task_11_input').value.toUpperCase();
  let output_string = '';
  let max_len = 0;
  let min_len = 0;
  let letters_ctr = 0;
  let sum_letters = 0;
  let space_ctr = 0;

  for (i = 0; i < input_string.length; ++i) {
    if (65 <= input_string.charCodeAt(i) && input_string.charCodeAt(i) <= 90) {
      letters_ctr++;
      sum_letters++;
    } else if (input_string[i] === ' ') {
        if (max_len < letters_ctr || max_len === 0)
          max_len = letters_ctr;  
        if (min_len > letters_ctr || min_len === 0)
          min_len = letters_ctr;
      letters_ctr = 0;
      space_ctr++;
    } else if (input_string[i] === '.') {
        if (max_len < letters_ctr || max_len === 0)
          max_len = letters_ctr;  
        if (min_len > letters_ctr || min_len === 0)
          min_len = letters_ctr;
        letters_ctr = 0;
    }
  }

  if (max_len < letters_ctr || max_len === 0)
    max_len = letters_ctr;  
  if (min_len > letters_ctr || min_len === 0)
    min_len = letters_ctr;

  output_string = "Максимальная длина - " + max_len;
  document.getElementById('task_11_output_1').value = output_string;
  output_string = "Минимальная длина - " + min_len;
  document.getElementById('task_11_output_2').value = output_string;
  output_string = "Среднее кол-во букв в слове - " + (sum_letters / (space_ctr + 1));
  document.getElementById('task_11_output_3').value = output_string;
}


function CalcTask12() {
  let input_string = document.getElementById('task_12_input').value;
  let str_arr = input_string.split('');
  let isPalindrome = true;
  let output_string = '';

  for (i = 0; i < str_arr.length; ++i) {
    if (str_arr[i] == ' ' || str_arr[i] == ',' || str_arr[i] == '.') {
      str_arr.splice(i, 1);
      i -= 1;
    }
  }

  let arr_len = str_arr.length;
  for (i = 0; i <arr_len; ++i) {
    if (str_arr[i] !== str_arr[arr_len - i - 1]) {
      isPalindrome = false;
      break;
    }
  }

  if (isPalindrome)
    output_string = "Палиндром";
  else
    output_string = "Не является палиндромом";
 
  document.getElementById('task_12_output').value = output_string;
}


function CalcTask13() {
  let address = document.getElementById('task_13_input').value;
  let isInvalid = false;
  let dog_place;
  let dot_place; 
  let output_string = '';
  
  dog_place = address.indexOf('@');
  dot_place = address.lastIndexOf('.');

  if (!(~dog_place)) {
    output_string += "Пропущен символ собаки";
    isInvalid = true;
  }

  if (address.lenght < 6) {
    output_string += "Слишком короткий адрес. Минимум - 6 символов";
    isInvalid = true;
  }

  if (dog_place === 0) {
    output_string += "До собаки необходим ещё хотя бы один символ";
    isInvalid = true;
  }

  if (dot_place < dog_place) {
    output_string += "Cправа от символа «@» должна быть, как минимум, одна точка";
    isInvalid = true;
  }

  if ((address.length - dot_place) < 3) {
    output_string += "Справа от последней точки должно быть, как минимум, 2 символа";
    isInvalid = true;
  }

  if (dot_place <= dog_place + 1 && dot_place !== -1) {
    output_string += "Между символом «@» и следующей за ним точкой должен быть, как минимум, один символ";
    isInvalid = true;
  }

  if (isInvalid)
    document.getElementById('task_13_output').value = output_string;
  else
   document.getElementById('task_13_output').value = "Адрес корректный!";
}


function CalcTask14() {
  let X = parseFloat(document.getElementById('task_14_input_1').value);
  let Y = parseFloat(document.getElementById('task_14_input_2').value);
  let Xc = parseFloat(document.getElementById('task_14_input_3').value);
  let Yc = parseFloat(document.getElementById('task_14_input_4').value);
  let R = parseFloat(document.getElementById('task_14_input_5').value);
  let output_string = '';

  if (Math.pow((X - Xc), 2) + Math.pow((Y - Yc), 2) <= Math.pow(R, 2))
    output_string += 'Точка попадает в круг!';
  else
    output_string += 'Точка не попадает в круг!'; 

  document.getElementById('task_14_output').value = output_string;
}


function CalcTask15() {
  let T = 0.1;
  let step = 0.05;
  let output_string = '';
  let Y;

  while (T <= 0.8) {
    Y = 4 * Math.sin(T) - 0.5 * Math.sin(T);
    output_string += ` T = ${T.toFixed(2)} => Y = ${Y.toFixed(5)}`;
    T += step;
  }

  document.getElementById('task_15_output').value = output_string;  
}


function CalcTask16() {
  const g = 9.80665;
  let V0 = parseFloat(document.getElementById('task_16_input_1').value);
  let t = parseFloat(document.getElementById('task_16_input_2').value);
  let output_string;

  if (V0 === 0.0) {
    output_string = "Деление на ноль не определено!";
    document.getElementById('task_16_output').value = output_string;
    return null; 
  }
  
  let result = (t * g) / (2 * V0);
  
  if (result > 1) {
    output_string = "Нулевой либо неопределённый угол!";
    document.getElementById('task_16_output').value = output_string;
    return null;
  }

  result = Math.asin(result);
  result /= Math.PI;
  result *= 180;

  output_string = "Угол броска: " + result.toFixed(2) + String.fromCharCode(176);
  document.getElementById('task_16_output').value = output_string;
}


function CalcTask17() {
  let id = parseInt(document.getElementById("task_17_input").value);
  let s;
  switch (id) {
      case 1:
          s = method1();
          break;
      case 2:
          s = method2();
          break;
      case 3:
          s = method3();
          break;
      case 4:
          s = method4();
          break;
      case 5:
          s = method5();
          break;
      case 6:
          s = method6();
          break;
      default:
          document.getElementById("task_17_output").value = "Такого варианта нет!";
  }


  function method1() {
      let a = parseInt(prompt("Введите сторону a:"));
      let b = parseInt(prompt("Введите сторону b:"));
      let c = parseInt(prompt("Введите сторону c:"));
      if (a + b < c || a + c < b || b + c < a) alert("Такой треугольник не существует");
      let p = (a + b + c) / 2;
      return Math.sqrt((p * (p - a) * (p - b) * (p - c)));
  }

  function method2() {
      let a = parseInt(prompt("Введите сторону a:"));
      let a1 = parseInt(prompt("Введите угл альфа:"));
      let a2 = parseInt(prompt("Введите угл бета:"));
      let a3 = parseInt(prompt("Введите угл гамма:"));
      if (a1 < -1 || a1 > 1 || a2 < -1 || a2 > 1 || a3 < -1 || a3 > 1) alert("Такой треугольник не существует");
      let p = 0.5 * Math.pow(a, 2) * (a2 * a3 / a1);
      return p;
  }

  function method3() {
      let a = parseInt(prompt("Введите сторону a:"));
      let b = parseInt(prompt("Введите сторону b:"));
      let a1 = parseInt(prompt("Введите угл альфа:"));
      return (a * b * Math.sin(a1)) / 2;
  }

  function method4() {
      alert("Треугольник должен быть прямоугольным");
      let a = parseInt(prompt("Введите сторону a:"));
      let b = parseInt(prompt("Введите сторону b:"));
      return (a * b) / 2;
  }

  function method5() {
      let h = parseInt(prompt("Введите высоту:"));
      let c = parseInt(prompt("Введите основание:"));
      return (h * c) / 2;
  }

  function method6() {
      let a = parseInt(prompt("Введите сторону a:"));
      let a1 = parseInt(prompt("Введите угл альфа:"));
      let a2 = parseInt(prompt("Введите угл бета:"));
      let a3 = parseInt(prompt("Введите угл гамма:"));
      return 0.5 * Math.pow(a1, 2) * (Math.sin(a1) * Math.sin(a3) / Math.sin(a2));
  }

  document.getElementById("task_17_output").value = "Площадь треугольника равна: " + s;
}


function CalcTask18() {
  let n = parseInt(document.getElementById('task_18_input').value);
  let fib_a = 0;
  let fib_b = 1;
  let fib_sum = 0;
  let fib_arr = new Array();
  fib_arr.push(fib_a);
  fib_arr.push(fib_b);

  let i = 0; 
  while(i < n - 2) {
    fib_sum = fib_a + fib_b;
    fib_a = fib_b;
    fib_b = fib_sum;
    i++;

    fib_arr.push(fib_b);
  }

  let output_string = fib_arr.join(', ');
  document.getElementById('task_18_output').value = output_string;
}


function CalcTask19() {
  let input_string = document.getElementById('task_19_input').value;
  let input_arr = input_string.split('');
  let len = input_arr.length;
  let used_symbols = new Array();

  for (i = 0; i < len; ++i) {
    if (used_symbols.indexOf(input_arr[i]) !== -1) {
      input_arr.splice(i, 1);
      i -= 1;
    } else {
      used_symbols.push(input_arr[i]);
    }
  }

  output_string = input_arr.join('');
  document.getElementById('task_19_output').value = output_string;
}


function CalcTask20() {
  n = parseInt(document.getElementById('task_20_input').value);

  let arr = new Array();
  let sum = 0;
  let rand_num;

  for (i = 0; i < n; ++i) {
    rand_num = Math.round(Math.random() * 10);
    sum += rand_num;
    arr.push(rand_num);
  }

  let output_string = arr.join(', ');
  document.getElementById('task_20_output_1').value = output_string;
  output_string = "Sum is " + sum;
  document.getElementById('task_20_output_2').value = output_string;
}