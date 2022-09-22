### Time Complexity dan Big-O Notation
Setiap programmer yang baik akan menggunakan cara yang paling efektif dan efisien dalam menyelesaikan suatu permasalahan. Dan untuk bisa melakukan hal tersebut, kita harus bisa meminimalisir kompleksitas dari algoritma yang kita gunakan.

Kompleksitas suatu algoritma dibagi menjadi 2, yaitu Time Complexity dan Space Complexity.

Time Complexity adalah seberapa lama waktu yang diperlukan untuk menjalankan suatu algoritma. Sedangkan Space Complexity adalah seberapa besar memori yang kita gunakan untuk menjalankan suatu algoritma. Dan disini kita hanya akan membahas tentang Time Complexity.


Apa itu Algoritma?

Algoritma adalah serangkaian proses yang dilakukan secara berurutan untuk menyelesaikan sebuah permasalahan. Algoritma bisa bermacam-macam tergantung kepada siapa yang membuat algoritma tersebut. Namun permasalahannya adalah algoritma mana yang lebih efektif dan efisien?

Time Complexity Analysis adalah suatu cara sederhana untuk mengetahui berapa lama waktu yang dibutuhkan untuk menjalankan suatu algoritma dengan input tertentu (n). Biasanya lebih dikenal dengan sebutan Big-O Notation.

Big-O Notation digunakan untuk mengukur tingkat kompleksitas suatu algoritma.

### Big-O Nation
Big-O Notation adalah cara untuk mengkonversi keseluruhan langkah-langkah suatu algoritma kedalam bentuk Aljabar, yaitu dengan menghiraukan konstanta yang lebih kecil dan koefisien yang tidak berdampak besar terhadap keseluruhan kompleksitas permasalahan yang diselesaikan oleh algoritma tersebut.

Mari kita lihat contoh dibawah ini:

Regular       Big-O
2             O(1)   --> It's just a constant number
2n + 10       O(n)   --> n has the largest effect
5n^2          O(n^2) --> n^2 has the largest effect

Sederhananya, semua contoh yang ada diatas mengatakan bahwa “kita hanya akan melihat faktor yang memiliki dampak paling besar terhadap nilai yang dihasilkan oleh algoritma tersebut”.

Terdapat beberapa macam **time complexity**, diantaranya :

### O(1) — Constant Time

Constant Time artinya banyaknya input yang diberikan kepada sebuah algoritma, tidak akan mempengaruhi waktu proses (runtime) dari algoritma tersebut.

let myArray = [1, 5, 0, 6, 1, 9, 9, 2];

function getFirst(input){

   return input[0]; // selalu melakukan 1 langkah
   
}

let firstEl = getFirst(myArray);

Dari contoh di atas, terdapat sebuah fungsi untuk mengambil elemen pertama dari sebuah input array. Kita bisa melihat bahwa berapapun jumlah array yang diberikan kepada fungsi tersebut, dia akan selalu melakukan 1 hal, yaitu mengambil elemen pertama. Itu artinya jumlah input yang diberikan tidak mempengaruhi waktu proses (runtime) dari algoritma tersebut.

![pic](https://miro.medium.com/max/1110/1*e-VhJyemSGWq_ynFsBb1_A.png)

### O(log n) — Logarithmic Time
Logarithmic Time artinya ketika kita memberikan input sebesar n terhadap sebuah fungsi, jumlah tahapan yang dilakukan oleh fungsi tersebut berkurang berdasarkan suatu faktor. Salah satu contohnya adalah algoritma Binary Search.

Binary Search adalah algoritma yang kita gunakan dalam mencari posisi nilai dari suatu array dengan cara ‘mengeliminasi’ setengah dari array input untuk mempercepat proses pencarian.

<p>
let sortedArray = [11, 24, 30, 43, 51, 61, 73, 86];<br>
function isExists(number, array){<br>
    var midPoint = Math.floor( array.length /2 );<br>
    if( array[midPoint] === num) return true;<br>
    let isFirstHalf = false;<br>
    if( array[midPoint] < num ) isFirstHalf = true;<br>
  
    else if( array[midpoint] > num ) isFirstHalf = false;<br>
    if (array.length == 1) return false;<br>
    else { <br>
        // memanggil fungsi yang sama dengan mengeleminiasi setengah dari input array<br>
        if (isFirstHalf) <br>
            return isExists(number, getFirstHalf(array));<br>
        else <br>
            return isExists(number, getSecondHalf(array));<br>
    }<br>
}<br>
isExists (24, sortedArray); // return true<br>
isExists (27, sortedArray); // return false<br>
</p>

*Note: Fungsi rekursif biasanya Logarithmic*

### O(n) — Linear Time
Linear Time adalah ketika runtime dari fungsi kita berbanding lurus dengan jumlah input yang diberikan.

let myArray = [1, 5, 0, 6, 1, 9, 9, 2];<br>
function getMax(input){<br>
    var max = 0;<br>
    for (var i=0; i<input.length; i++){<br>
        if (max < input[i])<br>
            max = input[i];<br>
    }<br>
    return max;<br>
}<br>
let maxNumber = getMax(myArray);<br>

Kita bisa melihat bahwa semakin banyak jumlah input yang diberikan, maka waktu proses/runtime dari fungsi tersebut akan semakin besar.

![](https://miro.medium.com/max/1106/1*VaFSvrt4lN3aKfDwuZR3Ow.png)

### O(n²) — Quadratic Time
Quadratic Time adalah ketika runtime dari fungsi kita adalah sebesar <br>
n^2<br>
dimana <br>
n<br>
adalah jumlah input dari fungsi tersebut. Hal tersebut bisa terjadi karena kita menjalankan fungsi linear didalam fungsi linear (n*n).<br>

let myArray = [1, 5, 0, 6, 1, 9, 9, 2];<br>
function sort(input){<br>
    var sortedArray = [];<br>
    for (var i=0; i<input.length; i++){ // O(n) <br>
        let min = input[i];<br>
        for (var j=i+1; i<input.length; i++){ // O(n)<br>
            if (input[i] < input[j])<br>
                min = input[j];<br>
        }<br>
        sortedArray.push(min);<br>
    }<br>
    return sortedArray;<br>
}<br>
let sortedArray = sort(myArray);<br>

![](https://miro.medium.com/max/640/1*2mYL6r8c2XVKXEG5oAUqZQ.png)

### O(2^n) — Exponential Time
Exponential Time biasanya digunakan dalam situasi dimana kita tidak terlalu tahu terhadap permasalahan yang dihadapi, sehingga mengharuskan kita mencoba setiap kombinasi dan permutasi dari semua kemungkinan.

![](https://miro.medium.com/max/1066/1*u7dzzW7DZegsJhEVfbcfNg.png)
### Kesimpulan
Sebagai programmer, kita sering kali dihadapkan dengan adanya beberapa solusi untuk sebuah permasalahan dan kita dibingungkan dengan pertanyaan “mana solusi yang lebih efisien?”.

Dengan memahami Big-O Notation, kita akan lebih mudah dalam melihat mana algoritma yang lebih efisien yang bisa kita gunakan untuk menyelesaikan permasalahan yang sedang dihadapi.
