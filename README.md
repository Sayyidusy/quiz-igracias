# kuis-auto-telyu
by mrzf833

masukan kode dibawah ini ke dalam inspect element bagian console pas di menu pilihan kuis

```
Array.prototype.random = function () {
  return this[Math.floor((Math.random()*this.length))];
}

let option = prompt("Masukkan pilihan yang diinginkan, mulai dari 0. Contoh input satu pilihan: 0. Contoh input pilihan acak: 0,1,2,3,4");
option = option.replaceAll(' ','');

let options = option.split(",");

$('div[id="radioX"]').each(function(index, value) {
  let terpilih = options.random();
  let panjangPilihan =  $(`div[id='radioX']:eq(${index}) li`).size();
  if(terpilih > (panjangPilihan - 1)){
    alert("Opsi tidak ada");
    $(`div[id='radioX'] li input`).attr('checked', false);
    return false;
  }
  $(`div[id='radioX']:eq(${index}) li:eq(${terpilih}) input`).attr('checked', true);
});

```
