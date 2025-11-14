### <p style="color: #11ff55">Môn học chỉ lý thuyết</p>
<p id="code_1">Lấy danh sách nhóm lớp học phần</p>

```javascript
document.querySelectorAll("div.col-12.col-md-4.classroom-section-item").forEach(e=>{console.log(e.querySelector('a[href="#"]').innerHTML+"---"+e.querySelector("a.btnDangKyHocPhan").id)});
```
<p id="code_2">Auto đăng ký lớp lý thuyết</p>

```javascript
var id= "Nhập ID nhóm lớp ở đây";
var activeTool = true;
var minDelay = 200, maxDelay = 1200, skipP = 0.2;

(async function loop(){
  while(activeTool){
    let d = Math.floor(Math.random()*(maxDelay-minDelay+1))+minDelay;
    await new Promise(r=>setTimeout(r,d));
    if(Math.random() < skipP) { console.log('skip'); continue; }
    try {
      document.getElementById(id)?.click();
      document.getElementById("btnDangKyLopHocPhanDaChon")?.click();
      console.log('clicked', new Date().toISOString());
    } catch(e){ console.warn('err',e); }
  }
})();

```

### <p style="color: #11ff55">Môn học có nhóm (Lý thuyết + Thực hành)</p>
<p id="code_3">Lấy danh sách lớp thực hành</p>

```javascript
document.querySelectorAll("div.col-12.col-md-3.classroom-section-item.box-hocphan.zoneNhomLopHocPhan").forEach(o=>{console.log(o.querySelector('a[href="#"]').innerHTML+"---"+o.querySelector("a.btnChonNhomLopHocPhan").id)});
```

<p id="code_4">Auto đăng ký nhóm lớp</p>

```javascript
var id_nhom = 'Nhập ID nhóm lớp ở đây';
var id_lop = 'Nhập ID lớp thực hành ở đây';

var activeTool = 1;
var minD = 300, maxD = 1200, skipP = 0.18;

(async function loop(){
  while(activeTool){
    let d = Math.random()*(maxD-minD)+minD;
    await new Promise(r=>setTimeout(r, d));
    if(Math.random() < skipP){ console.log('skip'); continue; }

    try{
      document.getElementById(id_nhom)?.click();
      document.getElementById(id_lop)?.click();
      document.getElementById("btnDangKyNhomLop")?.click();
      document.getElementById("btnDangKyLopHocPhanDaChon")?.click();
      console.log('clicked', new Date().toISOString());
    }catch(e){ console.warn('err', e); }
  }
})();

```
