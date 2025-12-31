<!-- INPUT -->
    <div class="box">
        <div class="identitas">
            <strong>Nama :</strong> Alya Rose K.N<br>
            <strong>NPM :</strong> 24120038
        </div>

        <h3>DATA NILAI MAHASISWA</h3>

        <label>Masukan NIM</label>
        <input type="text" id="nim">

        <label>Nama Mahasiswa</label>
        <input type="text" id="nama">

        <label>Nilai UTS</label>
        <input type="number" id="uts">

        <label>Nilai UAS</label>
        <input type="number" id="uas">

        <label>Nilai Tugas</label>
        <input type="number" id="tugas">

        <button onclick="hitung()">Proses</button>
        <button onclick="resetForm()">Batal</button>

        <p>
            UTS 30% | UAS 40% | TUGAS 30% <br>
            85–100 = A | 70–84 = B | 60–69 = C | 40–59 = D | &lt;40 = E
        </p>
    </div>

    <!-- OUTPUT -->
    <div class="box">
        <div class="identitas">
            <strong>Nama :</strong> Alya Rose K.N<br>
            <strong>NPM :</strong> 24120038
        </div>

        <h3>HASIL NILAI</h3>

        NIM : <span id="out_nim">-</span><br><br>
        Nama Mahasiswa : <span id="out_nama">-</span><br><br>
        Nilai UTS : <span id="out_uts">-</span><br><br>
        Nilai UAS : <span id="out_uas">-</span><br><br>
        Nilai Tugas : <span id="out_tugas">-</span><br><br>
        <strong>Index : <span id="out_index">-</span></strong>
    </div>

</div>

<script>
function hitung() {
    let nim = document.getElementById("nim").value;
    let nama = document.getElementById("nama").value;
    let uts = parseFloat(document.getElementById("uts").value);
    let uas = parseFloat(document.getElementById("uas").value);
    let tugas = parseFloat(document.getElementById("tugas").value);

    if (!nim || !nama || isNaN(uts) || isNaN(uas) || isNaN(tugas)) {
        alert("Semua data harus diisi!");
        return;
    }

    let nilaiAkhir = uts * 0.30 + uas * 0.40 + tugas * 0.30;
    let index = "";

    if (nilaiAkhir >= 85) index = "A";
    else if (nilaiAkhir >= 70) index = "B";
    else if (nilaiAkhir >= 60) index = "C";
    else if (nilaiAkhir >= 40) index = "D";
    else index = "E";

    document.getElementById("out_nim").innerText = nim;
    document.getElementById("out_nama").innerText = nama;
    document.getElementById("out_uts").innerText = uts;
    document.getElementById("out_uas").innerText = uas;
    document.getElementById("out_tugas").innerText = tugas;
    document.getElementById("out_index").innerText = index;
}

function resetForm() {
    document.querySelectorAll("input").forEach(input => input.value = "");
    document.querySelectorAll("span").forEach(span => span.innerText = "-");
}
</script>

</body>
</html>

