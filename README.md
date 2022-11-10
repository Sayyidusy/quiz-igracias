# kuis-auto-telyu


masukan kode dibawah ini ke dalam inspect elemen pas di menu pilihan kuis

```
Array.prototype.random = function () {
  return this[Math.floor((Math.random()*this.length))];
}

let option = prompt("masukan pilihan yang di mau. mulai dari atas dan dari 0. contoh input satu pilihan = 0. contoh pilihan random = 0,1,2");
option = option.replaceAll(' ','');

let options = option.split(",");

$('div[id="radioX"]').each(function(index, value) {
    let terpilih = options.random();
    let panjangPilihan =  $(`div[id='radioX']:eq(${index}) li`).size();
    if(terpilih > (panjangPilihan - 1)){
        alert("option tidak ada");
        $(`div[id='radioX'] li input`).attr('checked', false);
        return false;
    }
  $(`div[id='radioX']:eq(${index}) li:eq(${terpilih}) input`).attr('checked', true);
});

```
