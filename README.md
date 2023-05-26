# kuis-auto-telyu
by me

masukan kode dibawah ini ke dalam inspect element bagian console pas di menu pilihan kuis

```
Array.prototype.random = function () {
  return this[Math.floor((Math.random()*this.length))];
}

let minOptions = 1; // Jumlah minimum opsi
let maxOptions = 10; // Jumlah maksimum opsi

let numOptions = Math.floor(Math.random() * (maxOptions - minOptions + 1)) + minOptions; // Jumlah opsi secara acak
let options = [];

for (let i = 0; i < numOptions; i++) {
  options.push(i);
}

$('div[id="radioX"]').each(function(index, value) {
  let terpilih = options.random();
  let panjangPilihan = $(`div[id='radioX']:eq(${index}) li`).size();
  if (terpilih > (panjangPilihan - 1)) {
    alert("Opsi tidak ada");
    $(`div[id='radioX'] li input`).attr('checked', false);
    return false;
  }
  $(`div[id='radioX']:eq(${index}) li:eq(${terpilih}) input`).attr('checked', true);
});

```
