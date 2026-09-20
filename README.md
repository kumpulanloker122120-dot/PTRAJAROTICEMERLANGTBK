<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1">
<title>HR Raja Roti Cemerlang</title>
<style>
:root{
  --bg:#EFEAE0;
  --surface:#FFFFFF;
  --ink:#2B241C;
  --ink-soft:#5B5245;
  --muted:#8A8272;
  --border:#E1D9C8;
  --primary:#A8642A;
  --primary-dark:#7C4A1E;
  --primary-soft:#F3E4D2;
  --navy:#1F2A3C;
  --navy-soft:#2C3B52;
  --success:#3F7D4F;
  --success-soft:#E4F0E6;
  --danger:#B33F32;
  --danger-soft:#F7E4E1;
  --warning:#B5811F;
  --warning-soft:#FBF0DA;
  --radius:10px;
  --sidebar-w:248px;
  font-size:16px;
}
*{box-sizing:border-box;}
html,body{margin:0;padding:0;}
body{
  background:var(--bg);
  color:var(--ink);
  font-family:-apple-system,BlinkMacSystemFont,"Segoe UI",Roboto,Helvetica,Arial,sans-serif;
  line-height:1.45;
  -webkit-font-smoothing:antialiased;
}
button,input,select,textarea{font-family:inherit;font-size:1rem;}
button{cursor:pointer;}
a{color:var(--primary-dark);}
table{border-collapse:collapse;width:100%;}
.tabular{font-variant-numeric:tabular-nums;}

/* ===== Layout ===== */
#app{min-height:100vh;}
.login-wrap{
  min-height:100vh;display:flex;align-items:center;justify-content:center;
  background:linear-gradient(160deg,var(--navy) 0%,var(--navy-soft) 55%,var(--primary-dark) 130%);
  padding:20px;
}
.login-card{
  background:var(--surface);border-radius:14px;padding:38px 34px;width:100%;max-width:380px;
  box-shadow:0 24px 60px rgba(15,15,10,0.35);
}
.login-brand{font-size:1.05rem;color:var(--muted);margin-bottom:2px;}
.login-title{font-size:1.5rem;font-weight:700;margin:0 0 22px 0;color:var(--ink);}
.field{margin-bottom:16px;}
.field label{display:block;font-size:0.85rem;color:var(--ink-soft);margin-bottom:6px;font-weight:600;}
.field input,.field select,.field textarea{
  width:100%;padding:11px 12px;border:1px solid var(--border);border-radius:8px;
  background:#FBFAF7;color:var(--ink);transition:border-color .15s;
}
.field input:focus,.field select:focus,.field textarea:focus{
  outline:none;border-color:var(--primary);background:#fff;
}
.btn{
  display:inline-flex;align-items:center;justify-content:center;gap:6px;
  padding:10px 16px;border-radius:8px;border:1px solid transparent;font-weight:600;
  font-size:0.92rem;transition:filter .12s,transform .05s;white-space:nowrap;
}
.btn:active{transform:translateY(1px);}
.btn-primary{background:var(--primary);color:#fff;}
.btn-primary:hover{filter:brightness(1.08);}
.btn-block{width:100%;}
.btn-outline{background:transparent;border-color:var(--border);color:var(--ink);}
.btn-outline:hover{background:#F3EFE6;}
.btn-success{background:var(--success);color:#fff;}
.btn-success:hover{filter:brightness(1.1);}
.btn-danger{background:var(--danger);color:#fff;}
.btn-danger:hover{filter:brightness(1.1);}
.btn-sm{padding:6px 10px;font-size:0.82rem;border-radius:6px;}
.btn-navy{background:var(--navy);color:#fff;}
.btn:disabled{opacity:0.45;cursor:not-allowed;}
.login-demo{margin-top:20px;padding:12px 14px;background:#F6F2EA;border-radius:8px;font-size:0.78rem;color:var(--ink-soft);}
.login-demo b{color:var(--ink);}
.login-error{background:var(--danger-soft);color:var(--danger);padding:10px 12px;border-radius:8px;font-size:0.85rem;margin-bottom:14px;}

.shell{display:flex;min-height:100vh;}
.sidebar{
  width:var(--sidebar-w);background:var(--navy);color:#EDEEF0;flex-shrink:0;
  display:flex;flex-direction:column;position:fixed;top:0;bottom:0;left:0;
  transform:translateX(0);transition:transform .2s ease;z-index:40;
}
.sidebar-brand{padding:22px 20px 16px 20px;border-bottom:1px solid rgba(255,255,255,0.08);}
.sidebar-brand .name{font-weight:700;font-size:1.02rem;color:#fff;}
.sidebar-brand .sub{font-size:0.74rem;color:#A9B2C0;margin-top:2px;}
.sidebar-nav{flex:1;overflow-y:auto;padding:14px 10px;}
.sidebar-group{font-size:0.68rem;color:#8590A2;padding:14px 10px 6px 10px;letter-spacing:.02em;}
.sidebar-link{
  display:flex;align-items:center;gap:10px;padding:10px 12px;border-radius:8px;color:#D6D9DE;
  text-decoration:none;font-size:0.9rem;margin-bottom:2px;font-weight:500;
}
.sidebar-link:hover{background:rgba(255,255,255,0.06);}
.sidebar-link.active{background:var(--primary);color:#fff;}
.sidebar-foot{padding:14px 16px;border-top:1px solid rgba(255,255,255,0.08);}
.sidebar-user{font-size:0.85rem;color:#fff;font-weight:600;}
.sidebar-role{font-size:0.72rem;color:#A9B2C0;margin-bottom:10px;}

.main{margin-left:var(--sidebar-w);flex:1;min-width:0;display:flex;flex-direction:column;}
.topbar{
  background:var(--surface);border-bottom:1px solid var(--border);padding:14px 26px;
  display:flex;align-items:center;justify-content:space-between;position:sticky;top:0;z-index:20;
}
.topbar-title{font-size:1.15rem;font-weight:700;}
.hamburger{display:none;background:none;border:none;font-size:1.4rem;padding:4px 8px;}
.content{padding:24px 26px 90px 26px;flex:1;}

/* ===== Cards / stats ===== */
.grid{display:grid;gap:16px;}
.grid-4{grid-template-columns:repeat(4,1fr);}
.grid-3{grid-template-columns:repeat(3,1fr);}
.grid-2{grid-template-columns:repeat(2,1fr);}
.card{background:var(--surface);border:1px solid var(--border);border-radius:var(--radius);padding:18px 20px;}
.stat{border-left:4px solid var(--primary);}
.stat .num{font-size:1.9rem;font-weight:700;line-height:1;margin-bottom:6px;}
.stat .label{font-size:0.82rem;color:var(--muted);}
.stat.stat-success{border-color:var(--success);}
.stat.stat-warning{border-color:var(--warning);}
.stat.stat-danger{border-color:var(--danger);}
.stat.stat-navy{border-color:var(--navy);}

.section-title{font-size:1.02rem;font-weight:700;margin:28px 0 12px 0;}
.section-title:first-child{margin-top:0;}

.panel{background:var(--surface);border:1px solid var(--border);border-radius:var(--radius);overflow:hidden;}
.panel-head{padding:16px 20px;border-bottom:1px solid var(--border);display:flex;align-items:center;justify-content:space-between;gap:10px;flex-wrap:wrap;}
.panel-head h3{margin:0;font-size:1rem;}
.panel-body{padding:18px 20px;}
.toolbar{display:flex;gap:10px;flex-wrap:wrap;align-items:center;}
.toolbar input,.toolbar select{padding:8px 10px;border:1px solid var(--border);border-radius:7px;background:#FBFAF7;}

table.datatable{font-size:0.88rem;}
table.datatable th{
  text-align:left;padding:10px 14px;background:#F6F3EC;color:var(--ink-soft);
  font-weight:600;font-size:0.78rem;border-bottom:1px solid var(--border);white-space:nowrap;
}
table.datatable td{padding:10px 14px;border-bottom:1px solid var(--border);vertical-align:middle;}
table.datatable tr:last-child td{border-bottom:none;}
.table-wrap{overflow-x:auto;}
.empty-row{padding:30px;text-align:center;color:var(--muted);}

.badge{display:inline-block;padding:3px 9px;border-radius:20px;font-size:0.74rem;font-weight:600;}
.badge-success{background:var(--success-soft);color:var(--success);}
.badge-danger{background:var(--danger-soft);color:var(--danger);}
.badge-warning{background:var(--warning-soft);color:var(--warning);}
.badge-muted{background:#EDEAE1;color:var(--muted);}
.badge-navy{background:#E7EAEF;color:var(--navy);}

.modal-bg{
  position:fixed;inset:0;background:rgba(20,16,10,0.45);display:flex;align-items:flex-start;
  justify-content:center;padding:30px 16px;overflow-y:auto;z-index:100;
}
.modal{background:#fff;border-radius:12px;width:100%;max-width:640px;padding:24px 26px 26px 26px;margin:auto 0;}
.modal h3{margin-top:0;}
.modal-close{float:right;background:none;border:none;font-size:1.3rem;color:var(--muted);}

.attendance-hero{
  background:linear-gradient(135deg,var(--navy),var(--navy-soft));color:#fff;border-radius:14px;
  padding:26px 24px;margin-bottom:20px;
}
.attendance-hero .greet{font-size:1.2rem;font-weight:700;margin-bottom:2px;}
.attendance-hero .date{font-size:0.85rem;color:#C7CDD8;margin-bottom:18px;}
.attendance-times{display:flex;gap:26px;margin-bottom:20px;flex-wrap:wrap;}
.attendance-times .t-label{font-size:0.75rem;color:#B7C0CE;}
.attendance-times .t-val{font-size:1.5rem;font-weight:700;}
.attendance-actions{display:flex;gap:12px;flex-wrap:wrap;}
.attendance-actions .btn{padding:14px 22px;font-size:1rem;flex:1;min-width:150px;}
.gps-info{font-size:0.78rem;color:#C7CDD8;margin-top:12px;}

.toast-wrap{position:fixed;bottom:88px;left:50%;transform:translateX(-50%);z-index:200;display:flex;flex-direction:column;gap:8px;align-items:center;width:100%;pointer-events:none;}
.toast{background:var(--ink);color:#fff;padding:11px 18px;border-radius:8px;font-size:0.88rem;box-shadow:0 8px 20px rgba(0,0,0,0.25);max-width:90vw;}
.toast.success{background:var(--success);}
.toast.error{background:var(--danger);}

.bottom-nav{
  display:none;position:fixed;bottom:0;left:0;right:0;background:var(--surface);
  border-top:1px solid var(--border);z-index:40;padding:6px 4px;
}
.bottom-nav-inner{display:flex;justify-content:space-around;}
.bottom-nav a{
  display:flex;flex-direction:column;align-items:center;gap:2px;color:var(--muted);
  text-decoration:none;font-size:0.68rem;padding:6px 4px;flex:1;font-weight:600;
}
.bottom-nav a.active{color:var(--primary);}
.bn-icon{font-size:1.15rem;}

.overlay-dim{display:none;position:fixed;inset:0;background:rgba(0,0,0,0.35);z-index:39;}

.form-row-2{display:grid;grid-template-columns:1fr 1fr;gap:14px;}
.muted{color:var(--muted);}
.small{font-size:0.82rem;}
.mt-0{margin-top:0;}
.hint{font-size:0.78rem;color:var(--muted);margin-top:4px;}
.divider{height:1px;background:var(--border);margin:18px 0;}
.pill-nav{display:flex;gap:6px;flex-wrap:wrap;margin-bottom:16px;}
.pill-nav button{padding:7px 13px;border-radius:20px;border:1px solid var(--border);background:#fff;font-size:0.82rem;font-weight:600;color:var(--ink-soft);}
.pill-nav button.active{background:var(--navy);color:#fff;border-color:var(--navy);}
.pager{display:flex;gap:6px;justify-content:flex-end;align-items:center;padding:12px 20px;font-size:0.82rem;color:var(--muted);}
.pager button{border:1px solid var(--border);background:#fff;border-radius:6px;padding:5px 10px;}
.pager button:disabled{opacity:.4;}
.kv{display:grid;grid-template-columns:150px 1fr;gap:8px 14px;font-size:0.9rem;}
.kv div:nth-child(odd){color:var(--muted);}
.center{text-align:center;}
.right{text-align:right;}
.cal-grid{display:grid;grid-template-columns:repeat(7,1fr);gap:6px;}
.cal-cell{min-height:64px;border:1px solid var(--border);border-radius:8px;padding:6px;font-size:0.78rem;background:#FBFAF7;cursor:pointer;}
.cal-cell.today{border-color:var(--primary);}
.cal-cell .d{font-weight:700;margin-bottom:4px;}
.cal-dot{display:inline-block;width:6px;height:6px;border-radius:50%;background:var(--primary);margin-right:2px;}
.cal-cell.empty{background:transparent;border:none;}
.cal-cell.sel{outline:2px solid var(--navy);}

@media(max-width:900px){
  .sidebar{transform:translateX(-100%);}
  .sidebar.open{transform:translateX(0);}
  .main{margin-left:0;}
  .hamburger{display:inline-block;}
  .content{padding:16px 14px 90px 14px;}
  .grid-4{grid-template-columns:repeat(2,1fr);}
  .grid-3{grid-template-columns:1fr 1fr;}
  .grid-2{grid-template-columns:1fr;}
  .form-row-2{grid-template-columns:1fr;}
  .bottom-nav{display:block;}
  .overlay-dim.show{display:block;}
  .attendance-actions .btn{min-width:120px;padding:14px 10px;}
}
@media(max-width:520px){
  .grid-4{grid-template-columns:1fr 1fr;}
}
</style>
</head>
<body>
<div id="app"></div>
<div class="toast-wrap" id="toastWrap"></div>
<script>
/* =====================================================================
   HR RAJA ROTI CEMERLANG - APLIKASI HR INTERNAL
   Single-file client app. Data layer is isolated behind the DB object
   so it can be swapped for a real backend (Supabase/Firebase/MySQL/
   PostgreSQL) later without touching the UI code above it.
   ===================================================================== */

/* ---------------------------------------------------------------------
   1. DATA LAYER (Google Sheets via Apps Script)
   GANTI URL DI BAWAH INI dengan URL Web App Apps Script kamu setelah
   deploy (Extensions > Apps Script > tempel Code.gs > Deploy > New
   deployment > Web app > Execute as: Me > Who has access: Anyone).
   Ini SATU-SATUNYA baris yang perlu diubah di file ini.
--------------------------------------------------------------------- */
const API_URL = 'https://script.google.com/macros/s/AKfycbx7NXqQbyJDq7UCiWsfBMhByxZFjaU56NNXvgI1A1Go9m5Cz8tYvc9PGzhbKYQNfc8j/exec';
const DB_PREFIX = 'hrrc_'; // dipakai untuk session login di sessionStorage (tetap per-device)
const COLLECTIONS = ['users','employees','attendance','leaveRequests',
  'permissionRequests','overtimeRequests','auditLogs','officeSettings',
  'notifications','leaveTypes','payrollRuns','jadwalKerja','rosterShift'];

let CACHE = null; // mirror semua data dari Google Sheets, dimuat sekali saat startup

const DB = {
  get(name){
    if(!CACHE) return name === 'officeSettings' ? null : [];
    const v = CACHE[name];
    if(v === undefined) return name === 'officeSettings' ? null : [];
    return v;
  },
  set(name, value){
    CACHE[name] = value; // update memori dulu supaya UI tetap instan (synchronous seperti sebelumnya)
    fetch(API_URL, {
      method: 'POST',
      body: JSON.stringify({ action: 'save', collection: name, data: value })
    }).catch(() => toast('Gagal sinkron ke server. Cek koneksi internet.', 'error'));
    return value;
  },
  users(){ return this.get('users'); },
  employees(){ return this.get('employees'); },
  attendance(){ return this.get('attendance'); },
  leaveRequests(){ return this.get('leaveRequests'); },
  permissionRequests(){ return this.get('permissionRequests'); },
  overtimeRequests(){ return this.get('overtimeRequests'); },
  auditLogs(){ return this.get('auditLogs'); },
  officeSettings(){ return this.get('officeSettings'); },
  notifications(){ return this.get('notifications'); },
  leaveTypes(){ return this.get('leaveTypes'); },
  payrollRuns(){ return this.get('payrollRuns'); },
  jadwalKerja(){ return this.get('jadwalKerja'); },
  rosterShift(){ return this.get('rosterShift'); },
};

async function loadAllFromServer(){
  const res = await fetch(API_URL + '?action=getAll');
  CACHE = await res.json();
}

function uid(prefix){
  return (prefix||'ID') + '-' + Date.now().toString(36).toUpperCase() + Math.random().toString(36).slice(2,6).toUpperCase();
}

/* ---------------------------------------------------------------------
   2. SEED DATA (dijalankan cuma kalau spreadsheet-nya masih kosong)
--------------------------------------------------------------------- */
function seedIfEmpty(){
  if(CACHE.employees && CACHE.employees.length) return; // sudah ada data di Sheets, skip

  DB.set('officeSettings', {
    companyName: 'PT RAJA ROTI CEMERLANG',
    lat: -6.1623639,
    lng: 107.0060282,
    radius: 500,
    jamMasuk: '08:30',
    jamPulang: '17:00',
    batasKeterlambatan: 0,
    tanggalMulaiAbsensi: todayISO(),
    bpjsTkKaryawanPersen: 3,
    bpjsTkPerusahaanPersen: 6.24,
    bpjsKesehatanKaryawanPersen: 1,
    bpjsKesehatanPerusahaanPersen: 4,
    potonganTelatPerHari: 25000
  });

  DB.set('leaveTypes', [
    {id:'lt-1', nama:'Cuti Tahunan'},
    {id:'lt-2', nama:'Cuti Sakit'},
    {id:'lt-3', nama:'Cuti Melahirkan'},
    {id:'lt-4', nama:'Cuti Khusus'},
    {id:'lt-5', nama:'Lainnya'}
  ]);

  const employees = [
    {
      id:'EMP-001', nik:'3273010101900001', kk:'3273010000001001',
      nama:'Budi Santoso', email:'budi@rajacemerlang.com', hp:'081234500001',
      alamat:'Jl. Melong Raya No. 12, Cimahi', tempatLahir:'Bandung', tglLahir:'1990-01-01',
      joinDate:'2022-03-01', jabatan:'Staff Produksi', departemen:'Produksi',
      atasan:'Siti Aminah', atasanId:'EMP-002', status:'AKTIF', jadwalKerja:'SHIFT2',
      jenisKontrak:'PKWT', nomorKontrak:'PKWT/001/2025', kontrakMulai:'2025-06-01', kontrakSelesai: addDaysISO(new Date(),25)
    },
    {
      id:'EMP-002', nik:'3273010101880002', kk:'3273010000001002',
      nama:'Siti Aminah', email:'siti@rajacemerlang.com', hp:'081234500002',
      alamat:'Jl. Kopo No. 45, Bandung', tempatLahir:'Bandung', tglLahir:'1988-05-12',
      joinDate:'2019-01-15', jabatan:'Supervisor HR', departemen:'HR',
      atasan:'-', atasanId:'', status:'AKTIF',
      jenisKontrak:'PKWTT', nomorKontrak:'PKWTT/014/2019', kontrakMulai:'2019-01-15', kontrakSelesai:''
    },
    {
      id:'EMP-003', nik:'3273010101920003', kk:'3273010000001003',
      nama:'Andi Saputra', email:'andi@rajacemerlang.com', hp:'081234500003',
      alamat:'Jl. Soekarno Hatta No. 88, Bandung', tempatLahir:'Cimahi', tglLahir:'1992-08-20',
      joinDate:'2023-02-01', jabatan:'Staff Gudang', departemen:'Warehouse Logistik',
      atasan:'Siti Aminah', atasanId:'EMP-002', status:'AKTIF',
      jenisKontrak:'Probation', nomorKontrak:'PROB/022/2026', kontrakMulai:'2026-08-01', kontrakSelesai: addDaysISO(new Date(),55)
    },
    {
      id:'EMP-004', nik:'3273010101950004', kk:'3273010000001004',
      nama:'Rina', email:'rina@rajacemerlang.com', hp:'081234500004',
      alamat:'Jl. Dago No. 5, Bandung', tempatLahir:'Bandung', tglLahir:'1995-11-02',
      joinDate:'2024-06-10', jabatan:'Staff Finance', departemen:'FAT',
      atasan:'Siti Aminah', atasanId:'EMP-002', status:'AKTIF',
      jenisKontrak:'PKWT', nomorKontrak:'PKWT/019/2025', kontrakMulai:'2025-01-01', kontrakSelesai: addDaysISO(new Date(),-10)
    },
    {
      id:'EMP-005', nik:'3273010101930005', kk:'3273010000001005',
      nama:'Dewi Lestari', email:'dewi@rajacemerlang.com', hp:'081234500005',
      alamat:'Jl. Ahmad Yani No. 100, Bandung', tempatLahir:'Garut', tglLahir:'1993-04-18',
      joinDate:'2021-09-01', jabatan:'Staff Marketing', departemen:'Sales',
      atasan:'Siti Aminah', atasanId:'EMP-002', status:'AKTIF',
      jenisKontrak:'PKWTT', nomorKontrak:'PKWTT/009/2021', kontrakMulai:'2021-09-01', kontrakSelesai:''
    }
  ];
  DB.set('employees', employees);

  DB.set('users', [
    {id:'USR-1', email:'hrd@rajacemerlang.com', password:'hrd123', role:'HRD', employeeId:'EMP-002', active:true},
    {id:'USR-2', email:'budi@rajacemerlang.com', password:'123456', role:'KARYAWAN', employeeId:'EMP-001', active:true},
    {id:'USR-3', email:'andi@rajacemerlang.com', password:'123456', role:'KARYAWAN', employeeId:'EMP-003', active:true},
    {id:'USR-4', email:'rina@rajacemerlang.com', password:'123456', role:'KARYAWAN', employeeId:'EMP-004', active:true},
    {id:'USR-5', email:'dewi@rajacemerlang.com', password:'123456', role:'KARYAWAN', employeeId:'EMP-005', active:true}
  ]);

  DB.set('attendance', []);
  DB.set('leaveRequests', []);
  DB.set('permissionRequests', []);
  DB.set('overtimeRequests', []);
  DB.set('auditLogs', []);
  DB.set('notifications', []);
  DB.set('payrollRuns', []);
  DB.set('rosterShift', []);
  DB.set('jadwalKerja', defaultJadwalKerja());
}
function defaultJadwalKerja(){
  return [
    {kode:'STAFF', nama:'Staff Reguler', jamMasuk:'08:00', jamPulang:'16:00',
     jamMasukSabtu:'', jamPulangSabtu:'', kerjaSabtu:true, kerjaMinggu:false, overnight:false, bisaRoster:false},
    {kode:'SHIFT1', nama:'Shift 1 (Operator) 23:00-07:00', jamMasuk:'23:00', jamPulang:'07:00',
     jamMasukSabtu:'', jamPulangSabtu:'', kerjaSabtu:true, kerjaMinggu:false, overnight:true, bisaRoster:true},
    {kode:'SHIFT2', nama:'Shift 2 (Operator) 07:00-15:00', jamMasuk:'07:00', jamPulang:'15:00',
     jamMasukSabtu:'', jamPulangSabtu:'', kerjaSabtu:true, kerjaMinggu:false, overnight:false, bisaRoster:true},
    {kode:'SHIFT3', nama:'Shift 3 (Operator) 15:00-23:00', jamMasuk:'15:00', jamPulang:'23:00',
     jamMasukSabtu:'', jamPulangSabtu:'', kerjaSabtu:true, kerjaMinggu:false, overnight:false, bisaRoster:true}
  ];
}
// Dipanggil tiap boot, TERLEPAS dari status seed karyawan - supaya kalau ada fitur baru yang
// nambah koleksi master data (seperti Jadwal Kerja), instalasi yang sudah punya data karyawan
// dari sebelumnya tetap otomatis kebagian data defaultnya, bukan cuma instalasi baru dari nol.
function ensureMasterDataSeeded(){
  if(!CACHE.jadwalKerja || !CACHE.jadwalKerja.length){
    DB.set('jadwalKerja', defaultJadwalKerja());
  }
  if(!CACHE.rosterShift) DB.set('rosterShift', []);
  if(!CACHE.payrollRuns) DB.set('payrollRuns', []);

  // Instalasi yang sudah jalan dari sebelum fitur Alpha ada belum punya
  // tanggalMulaiAbsensi - kalau belum ada, tentukan otomatis: pakai tanggal
  // absen ASLI (jamMasuk terisi) paling awal yang sudah ada, atau kalau
  // belum pernah ada absen sama sekali, anggap sistem baru mulai HARI INI
  // (bukan mundur ke tanggal join karyawan yang jauh sebelum sistem dipakai).
  const settings = DB.officeSettings();
  if(settings && !settings.tanggalMulaiAbsensi){
    const tanggalAsli = DB.attendance().filter(a => a.jamMasuk).map(a => a.tanggal).sort();
    const mulai = tanggalAsli.length ? tanggalAsli[0] : todayISO();
    DB.set('officeSettings', Object.assign({}, settings, { tanggalMulaiAbsensi: mulai }));
  }
  cleanupPrematureAlpha();
}
// Buang record ALPHA yang salah ditandai untuk tanggal SEBELUM sistem ini
// benar-benar mulai dipakai (bug versi sebelumnya menghitung mundur terlalu jauh).
function cleanupPrematureAlpha(){
  const settings = DB.officeSettings();
  if(!settings || !settings.tanggalMulaiAbsensi) return;
  const attendance = DB.attendance();
  const cleaned = attendance.filter(a => !(a.statusMasuk === 'ALPHA' && a.tanggal < settings.tanggalMulaiAbsensi));
  if(cleaned.length !== attendance.length) DB.set('attendance', cleaned);
}

function addDaysISO(date, days){
  const d = new Date(date);
  d.setDate(d.getDate() + days);
  return d.toISOString().slice(0,10);
}

/* ---------------------------------------------------------------------
   3. GENERAL UTILITIES
--------------------------------------------------------------------- */
const DEPARTEMEN_GROUPS = [
  { grup: 'Produksi & Operasional', items: [
    'Produksi',
    'Penimbangan',
    'Mixing',
    'Molding',
    'Baking',
    'Crushing',
    'Packing',
    'Indexing',
    'Metal Detector',
    'Bubblecrumb',
    'Battercrumb',
    'Housekeeping Produksi',
    'Operasional'
  ]},
  { grup: 'Warehouse & Logistik', items: [
    'Warehouse RM',
    'Warehouse Logistik',
    'Warehouse'
  ]},
  { grup: 'Umum & Pendukung', items: [
    'Office Boy',
    'Security'
  ]},
  { grup: 'Manajemen & Korporat', items: [
    'Direktur Utama',
    'MTC',
    'Sales',
    'HR',
    'HRGA',
    'QAQC&PD',
    'Purchasing',
    'Corsec',
    'FAT'
  ]}
];
const EXCEL_IMPORT_EMPLOYEES = [{"id": "EMPX-001", "nama": "ROHIMIN", "nik": "3216010603940006", "kk": "", "email": "putribilqis1802@gmail.com", "hp": "088889314953", "alamat": "KP. Tambun Sungai Angke  RT/003 RW/006", "tempatLahir": "Bekasi", "tglLahir": "1991-01-05", "joinDate": "2018-02-24", "jabatan": "Leader", "departemen": "Produksi", "atasan": "", "atasanId": "", "status": "AKTIF", "jadwalKerja": "STAFF", "jenisKontrak": "PKWT", "nomorKontrak": "KK-1802025", "kontrakMulai": "", "kontrakSelesai": ""}, {"id": "EMPX-002", "nama": "ADAM JORDAN", "nik": "", "kk": "", "email": "", "hp": "", "alamat": "", "tempatLahir": "", "tglLahir": "", "joinDate": "2023-02-02", "jabatan": "Leader", "departemen": "Produksi", "atasan": "", "atasanId": "", "status": "AKTIF", "jadwalKerja": "STAFF", "jenisKontrak": "PKWT", "nomorKontrak": "KK-2302113", "kontrakMulai": "", "kontrakSelesai": ""}, {"id": "EMPX-003", "nama": "RAHMA AFIYANTO", "nik": "", "kk": "", "email": "", "hp": "", "alamat": "", "tempatLahir": "", "tglLahir": "", "joinDate": "2025-07-21", "jabatan": "Leader", "departemen": "Produksi", "atasan": "", "atasanId": "", "status": "AKTIF", "jadwalKerja": "STAFF", "jenisKontrak": "PKWT", "nomorKontrak": "KK-2507097", "kontrakMulai": "", "kontrakSelesai": ""}, {"id": "EMPX-004", "nama": "NUR TRI ATMOJO", "nik": "", "kk": "", "email": "", "hp": "", "alamat": "", "tempatLahir": "", "tglLahir": "", "joinDate": "2025-06-26", "jabatan": "Leader", "departemen": "Produksi", "atasan": "", "atasanId": "", "status": "AKTIF", "jadwalKerja": "STAFF", "jenisKontrak": "PKWT", "nomorKontrak": "KK-2506095", "kontrakMulai": "", "kontrakSelesai": ""}, {"id": "EMPX-005", "nama": "MUHAMAD DAHMAN", "nik": "", "kk": "", "email": "", "hp": "", "alamat": "", "tempatLahir": "", "tglLahir": "", "joinDate": "2025-09-11", "jabatan": "Quality Control", "departemen": "Produksi", "atasan": "", "atasanId": "", "status": "AKTIF", "jadwalKerja": "STAFF", "jenisKontrak": "PKWT", "nomorKontrak": "KK-2509111", "kontrakMulai": "", "kontrakSelesai": ""}, {"id": "EMPX-006", "nama": "WAHYUDIN", "nik": "3216010701880088", "kk": "", "email": "yudaykadafi@gmail.com", "hp": "089630174098", "alamat": "Kp. Bogor RT 002/030 Setia Asih, Tarumajaya", "tempatLahir": "Bekasi", "tglLahir": "1987-03-27", "joinDate": "2018-04-28", "jabatan": "Quality Control", "departemen": "Produksi", "atasan": "", "atasanId": "", "status": "AKTIF", "jadwalKerja": "STAFF", "jenisKontrak": "PKWT", "nomorKontrak": "KK-1804031", "kontrakMulai": "", "kontrakSelesai": ""}, {"id": "EMPX-007", "nama": "ALSA PRASESTA", "nik": "3216060612930013", "kk": "", "email": "alsaapra@gmail.com", "hp": "085156625073", "alamat": "Bumi Sani Permai Blok F.1 No.07 RT 05/14 Setiamekar", "tempatLahir": "Bekasi", "tglLahir": "1993-12-06", "joinDate": "2019-01-05", "jabatan": "Quality Control", "departemen": "Produksi", "atasan": "", "atasanId": "", "status": "AKTIF", "jadwalKerja": "STAFF", "jenisKontrak": "PKWT", "nomorKontrak": "KK-1901033", "kontrakMulai": "", "kontrakSelesai": ""}, {"id": "EMPX-008", "nama": "M AKBAR FAUZI", "nik": "3216021404000006", "kk": "", "email": "muhammadakbarf454@gmail.com", "hp": "085778297084", "alamat": "Kp. Kedaung RT 02/01 Kedungjaya, Babelan", "tempatLahir": "Bekasi", "tglLahir": "2000-01-02", "joinDate": "2020-07-06", "jabatan": "Operator Produksi", "departemen": "Penimbangan", "atasan": "", "atasanId": "", "status": "AKTIF", "jadwalKerja": "SHIFT2", "jenisKontrak": "PKWT", "nomorKontrak": "KK-2007047", "kontrakMulai": "", "kontrakSelesai": ""}, {"id": "EMPX-009", "nama": "SOFYAN HADI", "nik": "3216012508020002", "kk": "", "email": "sofyanhadii250822@gmail.com", "hp": "089662787900", "alamat": "Kp. Penggarutan RT 01/20 Setia Asih, Tarumajaya", "tempatLahir": "Bekasi", "tglLahir": "2002-08-25", "joinDate": "2022-09-27", "jabatan": "Operator Produksi", "departemen": "Penimbangan", "atasan": "", "atasanId": "", "status": "AKTIF", "jadwalKerja": "SHIFT2", "jenisKontrak": "PKWT", "nomorKontrak": "KK-2209125", "kontrakMulai": "", "kontrakSelesai": ""}, {"id": "EMPX-010", "nama": "FIKRAM", "nik": "3216160107970136", "kk": "", "email": "fhikramblues@gmail.com", "hp": "085715644519", "alamat": "Kp. Terusan RT 03/01 Lenggahsari, Cabangbungin", "tempatLahir": "Bekasi", "tglLahir": "1999-03-14", "joinDate": "2020-03-09", "jabatan": "Operator Produksi", "departemen": "Penimbangan", "atasan": "", "atasanId": "", "status": "AKTIF", "jadwalKerja": "SHIFT2", "jenisKontrak": "PKWT", "nomorKontrak": "KK-2003039", "kontrakMulai": "", "kontrakSelesai": ""}, {"id": "EMPX-011", "nama": "NURFAIH", "nik": "3216162206960003", "kk": "", "email": "sridewi2503@gmail.com", "hp": "085819476410", "alamat": "Kp. Terusan bulak Desa Lengah Sari Kec. Cabang BunginRT/03 RW/01", "tempatLahir": "", "tglLahir": "", "joinDate": "2024-01-03", "jabatan": "Operator Produksi", "departemen": "Penimbangan", "atasan": "", "atasanId": "", "status": "AKTIF", "jadwalKerja": "SHIFT2", "jenisKontrak": "Harian", "nomorKontrak": "KH-2401034", "kontrakMulai": "", "kontrakSelesai": ""}, {"id": "EMPX-012", "nama": "MUHAMMAD SUBUR", "nik": "", "kk": "", "email": "", "hp": "", "alamat": "", "tempatLahir": "", "tglLahir": "", "joinDate": "2022-12-19", "jabatan": "Operator Produksi", "departemen": "Mixing", "atasan": "", "atasanId": "", "status": "AKTIF", "jadwalKerja": "SHIFT2", "jenisKontrak": "PKWT", "nomorKontrak": "KK-2212120", "kontrakMulai": "", "kontrakSelesai": ""}, {"id": "EMPX-013", "nama": "MASPURI DASUKI", "nik": "3216011511940005", "kk": "", "email": "assegafalwi783@gmail.com", "hp": "089643666661", "alamat": "Kp. Pulo Kendal RT 001/002 Setia Asih, Tarumajaya", "tempatLahir": "Bekasi", "tglLahir": "1997-11-15", "joinDate": "2016-03-08", "jabatan": "Operator Produksi", "departemen": "Mixing", "atasan": "", "atasanId": "", "status": "AKTIF", "jadwalKerja": "SHIFT2", "jenisKontrak": "PKWT", "nomorKontrak": "KK-1603009", "kontrakMulai": "", "kontrakSelesai": ""}, {"id": "EMPX-014", "nama": "LUCKY TRI SETIOFANI", "nik": "3304011208010002", "kk": "", "email": "luckytry78@gmail.com", "hp": "088902908452", "alamat": "Jeblog RT 04/04 Karangsalam, Susukan", "tempatLahir": "Banjarnegara", "tglLahir": "2001-08-12", "joinDate": "2020-07-01", "jabatan": "Operator Produksi", "departemen": "Mixing", "atasan": "", "atasanId": "", "status": "AKTIF", "jadwalKerja": "SHIFT2", "jenisKontrak": "PKWT", "nomorKontrak": "KK-2007046", "kontrakMulai": "", "kontrakSelesai": ""}, {"id": "EMPX-015", "nama": "MAULIDAR MUHTAR", "nik": "", "kk": "", "email": "", "hp": "", "alamat": "", "tempatLahir": "", "tglLahir": "", "joinDate": "2023-01-15", "jabatan": "Operator Produksi", "departemen": "Mixing", "atasan": "", "atasanId": "", "status": "AKTIF", "jadwalKerja": "SHIFT2", "jenisKontrak": "PKWT", "nomorKontrak": "KK-2301119", "kontrakMulai": "", "kontrakSelesai": ""}, {"id": "EMPX-016", "nama": "ARDI SETIAWAN", "nik": "3216161709930006", "kk": "", "email": "ardisetiawan1728@gmail.com", "hp": "083890384232", "alamat": "Kp. Teluk Garut RT 04/02 SetiaJaya, Cabangbungin", "tempatLahir": "Bekasi", "tglLahir": "1993-09-17", "joinDate": "2021-02-17", "jabatan": "Operator Produksi", "departemen": "Molding", "atasan": "", "atasanId": "", "status": "AKTIF", "jadwalKerja": "SHIFT2", "jenisKontrak": "PKWT", "nomorKontrak": "KK-2102051", "kontrakMulai": "", "kontrakSelesai": ""}, {"id": "EMPX-017", "nama": "NALDI", "nik": "3216020712920013", "kk": "", "email": "naldibeat96@gmail.com", "hp": "083811401922", "alamat": "Kaliabang Dukuh RT 04/09 Pejuang, Medan Satria", "tempatLahir": "Bekasi", "tglLahir": "1992-12-07", "joinDate": "2018-04-02", "jabatan": "Operator Produksi", "departemen": "Molding", "atasan": "", "atasanId": "", "status": "AKTIF", "jadwalKerja": "SHIFT2", "jenisKontrak": "PKWT", "nomorKontrak": "KK-1804030", "kontrakMulai": "", "kontrakSelesai": ""}, {"id": "EMPX-018", "nama": "AHMAD RIFAIH", "nik": "3216011007030014", "kk": "", "email": "Ahmadpaong35@gmail.com", "hp": "083852768967", "alamat": "Kp. Tambun Semer Desa Pahlawan Setia Kec. Tarumajaya RT/003 RW/003", "tempatLahir": "Bekasi", "tglLahir": "2003-07-10", "joinDate": "2023-10-07", "jabatan": "Operator Produksi", "departemen": "Molding", "atasan": "", "atasanId": "", "status": "AKTIF", "jadwalKerja": "SHIFT2", "jenisKontrak": "Harian", "nomorKontrak": "KH-2310027", "kontrakMulai": "", "kontrakSelesai": ""}, {"id": "EMPX-019", "nama": "RIFKI", "nik": "3216052008010004", "kk": "", "email": "rr1602830@gmail.com", "hp": "089531686896", "alamat": "Kp. Gabus Singkil RT 01/01 Srijaya, Tambun Utara", "tempatLahir": "Bekasi", "tglLahir": "2001-08-20", "joinDate": "2022-10-15", "jabatan": "Operator Produksi", "departemen": "Molding", "atasan": "", "atasanId": "", "status": "AKTIF", "jadwalKerja": "SHIFT2", "jenisKontrak": "Harian", "nomorKontrak": "KH-2210013", "kontrakMulai": "", "kontrakSelesai": ""}, {"id": "EMPX-020", "nama": "DENI WIJAYA", "nik": "", "kk": "", "email": "", "hp": "", "alamat": "", "tempatLahir": "", "tglLahir": "", "joinDate": "2025-03-04", "jabatan": "Operator Produksi", "departemen": "Molding", "atasan": "", "atasanId": "", "status": "AKTIF", "jadwalKerja": "SHIFT2", "jenisKontrak": "PKWT", "nomorKontrak": "KK-2503107", "kontrakMulai": "", "kontrakSelesai": ""}, {"id": "EMPX-021", "nama": "IMAM", "nik": "3216011311940004", "kk": "", "email": "imamshafa1713@gmail.com", "hp": "081283937383", "alamat": "Kp. Bogor RT 001/030 Setia Asih, Tarumajaya", "tempatLahir": "Bekasi", "tglLahir": "1994-11-13", "joinDate": "2017-11-23", "jabatan": "Operator Produksi", "departemen": "Molding", "atasan": "", "atasanId": "", "status": "AKTIF", "jadwalKerja": "SHIFT2", "jenisKontrak": "PKWT", "nomorKontrak": "KK-1711018", "kontrakMulai": "", "kontrakSelesai": ""}, {"id": "EMPX-022", "nama": "A FAUZI", "nik": "3216012911920003", "kk": "", "email": "na901792@gmail.com", "hp": "089506864152", "alamat": "Kp. Penggarutan RT 001/020 Setia Asih, Tarumajaya", "tempatLahir": "Bekasi", "tglLahir": "1992-11-20", "joinDate": "2018-02-05", "jabatan": "Operator Produksi", "departemen": "Baking", "atasan": "", "atasanId": "", "status": "AKTIF", "jadwalKerja": "SHIFT2", "jenisKontrak": "PKWT", "nomorKontrak": "KK-1802023", "kontrakMulai": "", "kontrakSelesai": ""}, {"id": "EMPX-023", "nama": "MADINAH", "nik": "3216010206870015", "kk": "", "email": "sobari5686@gmail.com", "hp": "083127177100", "alamat": "Kp. Pisang Batu RT 001/001 Pahlawan Setia", "tempatLahir": "Bekasi", "tglLahir": "1987-06-02", "joinDate": "2016-02-10", "jabatan": "Operator Produksi", "departemen": "Baking", "atasan": "", "atasanId": "", "status": "AKTIF", "jadwalKerja": "SHIFT2", "jenisKontrak": "PKWT", "nomorKontrak": "KK-1602008", "kontrakMulai": "", "kontrakSelesai": ""}, {"id": "EMPX-024", "nama": "SARKAWI", "nik": "3216021708930016", "kk": "", "email": "sarkowi779@gmail.com", "hp": "0881025551768", "alamat": "Kp. Pulo Asem RT 10/06 Babelan Kota, Babelan", "tempatLahir": "Bekasi", "tglLahir": "1993-08-17", "joinDate": "2017-08-14", "jabatan": "Operator Produksi", "departemen": "Baking", "atasan": "", "atasanId": "", "status": "AKTIF", "jadwalKerja": "SHIFT2", "jenisKontrak": "PKWT", "nomorKontrak": "KK-1708015", "kontrakMulai": "", "kontrakSelesai": ""}, {"id": "EMPX-025", "nama": "RAHMAN RAMADIAH", "nik": "3216010201940010", "kk": "", "email": "nurainiria75@gmail.com", "hp": "089540552593", "alamat": "Kp. Pulo Kendal RT 01/02 Setia Asih, Tarumajaya", "tempatLahir": "Bekasi", "tglLahir": "1994-01-02", "joinDate": "2021-03-22", "jabatan": "Operator Produksi", "departemen": "Baking", "atasan": "", "atasanId": "", "status": "AKTIF", "jadwalKerja": "SHIFT2", "jenisKontrak": "PKWT", "nomorKontrak": "KK-2103053", "kontrakMulai": "", "kontrakSelesai": ""}, {"id": "EMPX-026", "nama": "SENDI CHANDRA", "nik": "", "kk": "", "email": "", "hp": "", "alamat": "", "tempatLahir": "", "tglLahir": "", "joinDate": "2021-06-07", "jabatan": "Operator Produksi", "departemen": "Baking", "atasan": "", "atasanId": "", "status": "AKTIF", "jadwalKerja": "SHIFT2", "jenisKontrak": "PKWT", "nomorKontrak": "KK-2106055", "kontrakMulai": "", "kontrakSelesai": ""}, {"id": "EMPX-027", "nama": "M SUBUR", "nik": "3216011810980006", "kk": "", "email": "msubur280@gmail.com", "hp": "089510711567", "alamat": "Kp. Pulo Timaha RT 11/07 Babelan Kota, Babelan", "tempatLahir": "Bekasi", "tglLahir": "1998-10-18", "joinDate": "2021-02-08", "jabatan": "Operator Produksi", "departemen": "Baking", "atasan": "", "atasanId": "", "status": "AKTIF", "jadwalKerja": "SHIFT2", "jenisKontrak": "PKWT", "nomorKontrak": "KK-2102049", "kontrakMulai": "", "kontrakSelesai": ""}, {"id": "EMPX-028", "nama": "MUSTAKIM", "nik": "3306082703970002", "kk": "", "email": "tmus65037@gmail.com", "hp": "085959012962", "alamat": "Pogungjurutengah RT 03/03 Pogungjurutengah, Bayan, Purworejo", "tempatLahir": "Purworejo", "tglLahir": "1997-03-27", "joinDate": "2017-09-29", "jabatan": "Operator Produksi", "departemen": "Baking", "atasan": "", "atasanId": "", "status": "AKTIF", "jadwalKerja": "SHIFT2", "jenisKontrak": "PKWT", "nomorKontrak": "KK-1709017", "kontrakMulai": "", "kontrakSelesai": ""}, {"id": "EMPX-029", "nama": "KHOERUL MUSTOFA", "nik": "", "kk": "", "email": "", "hp": "", "alamat": "", "tempatLahir": "", "tglLahir": "", "joinDate": "2024-09-21", "jabatan": "Operator Produksi", "departemen": "Baking", "atasan": "", "atasanId": "", "status": "AKTIF", "jadwalKerja": "SHIFT2", "jenisKontrak": "PKWT", "nomorKontrak": "KK-2409109", "kontrakMulai": "", "kontrakSelesai": ""}, {"id": "EMPX-030", "nama": "RAHMAT ARDI", "nik": "3216022709000014", "kk": "", "email": "rahmatardiyusup@gmail.com", "hp": "089530221511", "alamat": "Kp. Kedaung RT 09/03 Kedung Pengawas, Babelan", "tempatLahir": "Bekasi", "tglLahir": "2000-09-27", "joinDate": "2021-04-28", "jabatan": "Operator Produksi", "departemen": "Crushing", "atasan": "", "atasanId": "", "status": "AKTIF", "jadwalKerja": "SHIFT2", "jenisKontrak": "PKWT", "nomorKontrak": "KK-2104122", "kontrakMulai": "", "kontrakSelesai": ""}, {"id": "EMPX-031", "nama": "ASMAWI ASKO", "nik": "3216020709880021", "kk": "", "email": "asmawiasko28@gmail.com", "hp": "08993476576", "alamat": "Kp. Pulo Asem RT 10/06 Babelan Kota, Babelan", "tempatLahir": "", "tglLahir": "", "joinDate": "2020-06-30", "jabatan": "Operator Produksi", "departemen": "Crushing", "atasan": "", "atasanId": "", "status": "AKTIF", "jadwalKerja": "SHIFT2", "jenisKontrak": "PKWT", "nomorKontrak": "KK-2006045", "kontrakMulai": "", "kontrakSelesai": ""}, {"id": "EMPX-032", "nama": "REFANDA PERDANA", "nik": "3306040206040001", "kk": "", "email": "refandaperdana305@gmail.com", "hp": "087756870905", "alamat": "Bagelen RT 03/01 Bagelen, Bagelen", "tempatLahir": "Purworejo", "tglLahir": "2004-06-02", "joinDate": "2022-12-28", "jabatan": "Operator Produksi", "departemen": "Crushing", "atasan": "", "atasanId": "", "status": "AKTIF", "jadwalKerja": "SHIFT2", "jenisKontrak": "PKWT", "nomorKontrak": "KK-2212123", "kontrakMulai": "", "kontrakSelesai": ""}, {"id": "EMPX-033", "nama": "NAWI SAPUTRA", "nik": "3216010603000009", "kk": "", "email": "nawisaputra36@gmail.com", "hp": "087886882731", "alamat": "Kp. Tambun Baru RT 04/02 Pahlawan Setia, Tarumajaya", "tempatLahir": "Bekasi", "tglLahir": "2000-06-03", "joinDate": "2020-05-18", "jabatan": "Operator Produksi", "departemen": "Crushing", "atasan": "", "atasanId": "", "status": "AKTIF", "jadwalKerja": "SHIFT2", "jenisKontrak": "PKWT", "nomorKontrak": "KK-2005042", "kontrakMulai": "", "kontrakSelesai": ""}, {"id": "EMPX-034", "nama": "ARDIANSYAH", "nik": "3216023009000009", "kk": "", "email": "aa1689952@gmail.com", "hp": "083848442641", "alamat": "Kp. Pulo Timaha RT 01/09 Babelan Kota, Babelan", "tempatLahir": "Bekasi", "tglLahir": "2001-07-05", "joinDate": "2023-01-22", "jabatan": "Operator Produksi", "departemen": "Packing", "atasan": "", "atasanId": "", "status": "AKTIF", "jadwalKerja": "SHIFT2", "jenisKontrak": "PKWT", "nomorKontrak": "KK-2301115", "kontrakMulai": "", "kontrakSelesai": ""}, {"id": "EMPX-035", "nama": "FAID SAEPULOH", "nik": "3216010212980006", "kk": "", "email": "faizamburadul1719@gmail.com", "hp": "0895396298401", "alamat": "Kp. Pulo Kendal RT 02/03 Setia Asih, Tarumajaya", "tempatLahir": "Bekasi", "tglLahir": "1998-12-02", "joinDate": "2021-03-05", "jabatan": "Operator Produksi", "departemen": "Packing", "atasan": "", "atasanId": "", "status": "AKTIF", "jadwalKerja": "SHIFT2", "jenisKontrak": "PKWT", "nomorKontrak": "KK-2103052", "kontrakMulai": "", "kontrakSelesai": ""}, {"id": "EMPX-036", "nama": "WAWAN", "nik": "3216010501840010", "kk": "", "email": "wawanfayad@gmail.com", "hp": "083813944910", "alamat": "Kp. Pulo Kendal RT 01/03 Setia Asih, Tarumajaya", "tempatLahir": "Bekasi", "tglLahir": "1984-01-05", "joinDate": "2019-09-13", "jabatan": "Operator Produksi", "departemen": "Packing", "atasan": "", "atasanId": "", "status": "AKTIF", "jadwalKerja": "SHIFT2", "jenisKontrak": "PKWT", "nomorKontrak": "KK-1909038", "kontrakMulai": "", "kontrakSelesai": ""}, {"id": "EMPX-037", "nama": "SUHENDRA", "nik": "3216010701870058", "kk": "", "email": "sh6847125@gmail.com", "hp": "087780514721", "alamat": "Kp. Sawah RT 001/002 Setia Asih, Tarumajaya", "tempatLahir": "Bekasi", "tglLahir": "1987-03-22", "joinDate": "2017-12-14", "jabatan": "Operator Produksi", "departemen": "Mixing", "atasan": "", "atasanId": "", "status": "AKTIF", "jadwalKerja": "SHIFT2", "jenisKontrak": "PKWT", "nomorKontrak": "KK-1712021", "kontrakMulai": "", "kontrakSelesai": ""}, {"id": "EMPX-038", "nama": "KELVIN HADI GUNAWAN", "nik": "3216011812030006", "kk": "", "email": "kelvinhadigunawan792@gmail.com", "hp": "085780329873", "alamat": "Kp. Pulo Kendal RT 001/003 Setia Asih, Tarumajaya", "tempatLahir": "Bekasi", "tglLahir": "2000-12-18", "joinDate": "2017-09-27", "jabatan": "Operator Produksi", "departemen": "Packing", "atasan": "", "atasanId": "", "status": "AKTIF", "jadwalKerja": "SHIFT2", "jenisKontrak": "PKWT", "nomorKontrak": "KK-1709016", "kontrakMulai": "", "kontrakSelesai": ""}, {"id": "EMPX-039", "nama": "SYAMSUL ARIFIN", "nik": "3275030108950028", "kk": "", "email": "acul.sagle69@gmail.com", "hp": "089658413952", "alamat": "Kaliabang Rorotan RT 002/006 Kaliabang Tengah, Bekasi Utara", "tempatLahir": "Bekasi", "tglLahir": "1995-08-01", "joinDate": "2018-03-19", "jabatan": "Operator Produksi", "departemen": "Packing", "atasan": "", "atasanId": "", "status": "AKTIF", "jadwalKerja": "SHIFT2", "jenisKontrak": "PKWT", "nomorKontrak": "KK-1803029", "kontrakMulai": "", "kontrakSelesai": ""}, {"id": "EMPX-040", "nama": "MUSLIM", "nik": "3216010507940004", "kk": "", "email": "ajkomeng22@gmail.com", "hp": "081213036341", "alamat": "Kp. Pulo Timaha", "tempatLahir": "Bekasi", "tglLahir": "1994-07-05", "joinDate": "2022-12-11", "jabatan": "Operator Produksi", "departemen": "Packing", "atasan": "", "atasanId": "", "status": "AKTIF", "jadwalKerja": "SHIFT2", "jenisKontrak": "Harian", "nomorKontrak": "KH-2212012", "kontrakMulai": "", "kontrakSelesai": ""}, {"id": "EMPX-041", "nama": "SAHRUL GUNAWAN", "nik": "3216012503990001", "kk": "", "email": "sahrulsilvia081@gmail.com", "hp": "085775789854", "alamat": "Kp. Pulo Kendal RT 02/03 Setia Asih, Tarumajaya", "tempatLahir": "Bekasi", "tglLahir": "1997-03-25", "joinDate": "2021-02-08", "jabatan": "Operator Produksi", "departemen": "Packing", "atasan": "", "atasanId": "", "status": "AKTIF", "jadwalKerja": "SHIFT2", "jenisKontrak": "PKWT", "nomorKontrak": "KK-2102048", "kontrakMulai": "", "kontrakSelesai": ""}, {"id": "EMPX-042", "nama": "ROKHMAT YUNIANTO", "nik": "3275032406930014", "kk": "", "email": "rohmatyunianto48@gmail.com", "hp": "089655500152", "alamat": "JL. KH. Muchtar Tabrani RT 001/003 Perwira, Bekasi Utara", "tempatLahir": "Purworejo", "tglLahir": "1993-06-05", "joinDate": "2017-07-17", "jabatan": "Operator Produksi", "departemen": "Indexing", "atasan": "", "atasanId": "", "status": "AKTIF", "jadwalKerja": "SHIFT2", "jenisKontrak": "PKWT", "nomorKontrak": "KK-1707013", "kontrakMulai": "", "kontrakSelesai": ""}, {"id": "EMPX-043", "nama": "ISMAIL MARZUKI", "nik": "3216160112900008", "kk": "", "email": "Lurdoy63@gmail.com", "hp": "083815716731", "alamat": "Kp. Bugis Utara RT 09 RW 02 Tanah Baru, Pakis Jaya", "tempatLahir": "Bekasi", "tglLahir": "1990-12-01", "joinDate": "2019-08-21", "jabatan": "Operator Produksi", "departemen": "Indexing", "atasan": "", "atasanId": "", "status": "AKTIF", "jadwalKerja": "SHIFT2", "jenisKontrak": "PKWT", "nomorKontrak": "KK-1908036", "kontrakMulai": "", "kontrakSelesai": ""}, {"id": "EMPX-044", "nama": "SAEPUL ANWAR", "nik": "3216020508030003", "kk": "", "email": "anwarpaeng121@gmail.com", "hp": "089635696637", "alamat": "Kp. Wates RT 01/06 Kedungjaya, Babelan", "tempatLahir": "Bekasi", "tglLahir": "1999-05-20", "joinDate": "2020-05-11", "jabatan": "Operator Produksi", "departemen": "Indexing", "atasan": "", "atasanId": "", "status": "AKTIF", "jadwalKerja": "SHIFT2", "jenisKontrak": "PKWT", "nomorKontrak": "KK-2005040", "kontrakMulai": "", "kontrakSelesai": ""}, {"id": "EMPX-045", "nama": "GILANG ADI PRASETYO", "nik": "", "kk": "", "email": "", "hp": "", "alamat": "", "tempatLahir": "", "tglLahir": "", "joinDate": "2025-12-22", "jabatan": "Operator Produksi", "departemen": "Metal Detector", "atasan": "", "atasanId": "", "status": "AKTIF", "jadwalKerja": "SHIFT2", "jenisKontrak": "PKWT", "nomorKontrak": "KK-2212124", "kontrakMulai": "", "kontrakSelesai": ""}, {"id": "EMPX-046", "nama": "MALIK AL ASLAM", "nik": "3216012508010002", "kk": "", "email": "malikalaslam08@gmail.com", "hp": "089654786720", "alamat": "Kp. Tanah Tinggi RT 01/023 Setia Asih, Traumajaya", "tempatLahir": "Bekasi", "tglLahir": "2001-08-25", "joinDate": "2022-11-16", "jabatan": "Operator Produksi", "departemen": "Metal Detector", "atasan": "", "atasanId": "", "status": "AKTIF", "jadwalKerja": "SHIFT2", "jenisKontrak": "PKWT", "nomorKontrak": "KK-2211124", "kontrakMulai": "", "kontrakSelesai": ""}, {"id": "EMPX-047", "nama": "ABDULOH", "nik": "", "kk": "", "email": "", "hp": "", "alamat": "", "tempatLahir": "", "tglLahir": "", "joinDate": "2025-03-04", "jabatan": "Operator Produksi", "departemen": "Metal Detector", "atasan": "", "atasanId": "", "status": "AKTIF", "jadwalKerja": "SHIFT2", "jenisKontrak": "Harian", "nomorKontrak": "KH-2503051", "kontrakMulai": "", "kontrakSelesai": ""}, {"id": "EMPX-048", "nama": "ADE ADRIANSYAH", "nik": "", "kk": "", "email": "", "hp": "", "alamat": "", "tempatLahir": "", "tglLahir": "", "joinDate": "2025-07-21", "jabatan": "Operator Produksi", "departemen": "Metal Detector", "atasan": "", "atasanId": "", "status": "AKTIF", "jadwalKerja": "SHIFT2", "jenisKontrak": "Harian", "nomorKontrak": "KH-2507050", "kontrakMulai": "", "kontrakSelesai": ""}, {"id": "EMPX-049", "nama": "SOKMA PANGGIH PRAHORO", "nik": "3306012504990002", "kk": "", "email": "panggih328@gmail.com", "hp": "081228520334", "alamat": "Grabag RT 03/03 Grabag, Kab. Purworejo", "tempatLahir": "Purworejo", "tglLahir": "1999-04-25", "joinDate": "2023-12-21", "jabatan": "Operator Produksi", "departemen": "Metal Detector", "atasan": "", "atasanId": "", "status": "AKTIF", "jadwalKerja": "SHIFT2", "jenisKontrak": "PKWT", "nomorKontrak": "KK-2312126", "kontrakMulai": "", "kontrakSelesai": ""}, {"id": "EMPX-050", "nama": "ADJI PRATAMA", "nik": "3216010206010009", "kk": "", "email": "ajibibir06@gmail.com", "hp": "085883531612", "alamat": "Kp. Pulo Kendal RT 01/03 Setia Asih, Tarumajaya", "tempatLahir": "Bekasi", "tglLahir": "2001-02-06", "joinDate": "2021-02-08", "jabatan": "Operator Produksi", "departemen": "Metal Detector", "atasan": "", "atasanId": "", "status": "AKTIF", "jadwalKerja": "SHIFT2", "jenisKontrak": "PKWT", "nomorKontrak": "KK-2102050", "kontrakMulai": "", "kontrakSelesai": ""}, {"id": "EMPX-051", "nama": "EGA AZIZ", "nik": "", "kk": "", "email": "", "hp": "", "alamat": "", "tempatLahir": "", "tglLahir": "", "joinDate": "", "jabatan": "Operator Produksi", "departemen": "Bubblecrumb", "atasan": "", "atasanId": "", "status": "AKTIF", "jadwalKerja": "SHIFT2", "jenisKontrak": "PKWT", "nomorKontrak": "KK-2409108", "kontrakMulai": "", "kontrakSelesai": ""}, {"id": "EMPX-052", "nama": "MUKHLIS", "nik": "3216011105840003", "kk": "", "email": "salwazatilhulwani@gmail.com", "hp": "0895602425166", "alamat": "Kp. Penggarutan RT 002/028 Setia Asih, Tarumajaya", "tempatLahir": "Bekasi", "tglLahir": "1984-05-11", "joinDate": "2016-06-15", "jabatan": "Operator Produksi", "departemen": "Bubblecrumb", "atasan": "", "atasanId": "", "status": "AKTIF", "jadwalKerja": "SHIFT2", "jenisKontrak": "PKWT", "nomorKontrak": "KK-1606011", "kontrakMulai": "", "kontrakSelesai": ""}, {"id": "EMPX-053", "nama": "SISWANTO", "nik": "3328161608920004", "kk": "", "email": "cak.onjo92@gmail.com", "hp": "085692937403", "alamat": "Kp. Pulo Kendal RT 01/03 Setia Asih, Tarumajaya", "tempatLahir": "Tegal", "tglLahir": "1992-08-16", "joinDate": "2022-11-29", "jabatan": "Operator Produksi", "departemen": "Bubblecrumb", "atasan": "", "atasanId": "", "status": "AKTIF", "jadwalKerja": "SHIFT2", "jenisKontrak": "Harian", "nomorKontrak": "KH-2211010", "kontrakMulai": "", "kontrakSelesai": ""}, {"id": "EMPX-054", "nama": "ABDUL KHOLIK", "nik": "", "kk": "", "email": "", "hp": "", "alamat": "", "tempatLahir": "", "tglLahir": "", "joinDate": "2025-03-04", "jabatan": "Operator Produksi", "departemen": "Bubblecrumb", "atasan": "", "atasanId": "", "status": "AKTIF", "jadwalKerja": "SHIFT2", "jenisKontrak": "Harian", "nomorKontrak": "KH-2503052", "kontrakMulai": "", "kontrakSelesai": ""}, {"id": "EMPX-055", "nama": "M NURFAIN", "nik": "", "kk": "", "email": "", "hp": "", "alamat": "", "tempatLahir": "", "tglLahir": "", "joinDate": "2023-11-27", "jabatan": "Operator Produksi", "departemen": "Bubblecrumb", "atasan": "", "atasanId": "", "status": "AKTIF", "jadwalKerja": "SHIFT2", "jenisKontrak": "Harian", "nomorKontrak": "KH-2311032", "kontrakMulai": "", "kontrakSelesai": ""}, {"id": "EMPX-056", "nama": "SIGIT HARYADI", "nik": "3216010506010007", "kk": "", "email": "haryadisigit44@gmail.com", "hp": "085710907653", "alamat": "Kp. Pulo Kendal RT 01/03 Setia Asih, Tarumajaya", "tempatLahir": "Bekasi", "tglLahir": "2001-06-05", "joinDate": "2022-11-07", "jabatan": "Operator Produksi", "departemen": "Battercrumb", "atasan": "", "atasanId": "", "status": "AKTIF", "jadwalKerja": "SHIFT2", "jenisKontrak": "Harian", "nomorKontrak": "KH-2211014", "kontrakMulai": "", "kontrakSelesai": ""}, {"id": "EMPX-057", "nama": "M DAWAM RIZKI", "nik": "3216012802980002", "kk": "", "email": "muhammaddawamrizki@gmail.com", "hp": "081389207571", "alamat": "Kp. Pulo Kendal RT 01/03 Setia Asih, Tarumajaya", "tempatLahir": "Bekasi", "tglLahir": "1999-07-31", "joinDate": "2022-08-25", "jabatan": "Operator Produksi", "departemen": "Battercrumb", "atasan": "", "atasanId": "", "status": "AKTIF", "jadwalKerja": "SHIFT2", "jenisKontrak": "Harian", "nomorKontrak": "KH-2208007", "kontrakMulai": "", "kontrakSelesai": ""}, {"id": "EMPX-058", "nama": "HASAN BASRI", "nik": "3216161408910004", "kk": "", "email": "boackhasan@gmail.com", "hp": "08561831335", "alamat": "Kp. Teluk Garut RT 04/02 Setia Jaya, Cabangbungin", "tempatLahir": "Bekasi", "tglLahir": "1991-08-14", "joinDate": "2022-12-12", "jabatan": "Operator Produksi", "departemen": "Battercrumb", "atasan": "", "atasanId": "", "status": "AKTIF", "jadwalKerja": "SHIFT2", "jenisKontrak": "Harian", "nomorKontrak": "KH-2212015", "kontrakMulai": "", "kontrakSelesai": ""}, {"id": "EMPX-059", "nama": "FARHAN ANGGI", "nik": "3275020706030006", "kk": "", "email": "farhanangimaulana@gmail.com", "hp": "088214573596", "alamat": "Kp. Penggarutan RT 01/20 Setia Asih, Tarumajaya", "tempatLahir": "Bekasi", "tglLahir": "2003-06-07", "joinDate": "2022-10-07", "jabatan": "Operator Produksi", "departemen": "Battercrumb", "atasan": "", "atasanId": "", "status": "AKTIF", "jadwalKerja": "SHIFT2", "jenisKontrak": "Harian", "nomorKontrak": "KH-2210011", "kontrakMulai": "", "kontrakSelesai": ""}, {"id": "EMPX-060", "nama": "M SUMITO", "nik": "3216012907960004", "kk": "", "email": "itomuhamad97@gmail.com", "hp": "081318277342", "alamat": "Kp. Tikungan RT 01/15 Segarajaya, Tarumajaya", "tempatLahir": "Jakarta", "tglLahir": "1996-06-20", "joinDate": "2016-05-15", "jabatan": "Operator Warehouse", "departemen": "Warehouse RM", "atasan": "", "atasanId": "", "status": "AKTIF", "jadwalKerja": "SHIFT2", "jenisKontrak": "PKWT", "nomorKontrak": "KK-1605010", "kontrakMulai": "", "kontrakSelesai": ""}, {"id": "EMPX-061", "nama": "ANGGA RIBOWO", "nik": "3216011211940009", "kk": "", "email": "Panjul11245@gmail.com", "hp": "085694053094", "alamat": "KP.Pulo kendal RT/002 RT/003 Kel. Setia asih ,Tarumajaya", "tempatLahir": "", "tglLahir": "", "joinDate": "2023-09-16", "jabatan": "Operator Warehouse", "departemen": "Warehouse RM", "atasan": "", "atasanId": "", "status": "AKTIF", "jadwalKerja": "SHIFT2", "jenisKontrak": "Harian", "nomorKontrak": "KH-2309026", "kontrakMulai": "", "kontrakSelesai": ""}, {"id": "EMPX-062", "nama": "IBNU HAKIM", "nik": "", "kk": "", "email": "", "hp": "", "alamat": "", "tempatLahir": "", "tglLahir": "", "joinDate": "2025-03-03", "jabatan": "Operator Warehouse", "departemen": "Warehouse Logistik", "atasan": "", "atasanId": "", "status": "AKTIF", "jadwalKerja": "SHIFT2", "jenisKontrak": "PKWT", "nomorKontrak": "KK-2503086", "kontrakMulai": "", "kontrakSelesai": ""}, {"id": "EMPX-063", "nama": "ZAINUL HAMZAH", "nik": "3216012803930002", "kk": "", "email": "zainulhamzah222@gmail.com", "hp": "085714695002", "alamat": "Kp. Pulo Kendal RT 002/003 Setia Asih, Tarumajaya", "tempatLahir": "Bekasi", "tglLahir": "1993-03-28", "joinDate": "2019-03-04", "jabatan": "Operator Warehouse", "departemen": "Warehouse Logistik", "atasan": "", "atasanId": "", "status": "AKTIF", "jadwalKerja": "SHIFT2", "jenisKontrak": "PKWT", "nomorKontrak": "KK-1903035", "kontrakMulai": "", "kontrakSelesai": ""}, {"id": "EMPX-064", "nama": "YUDHA GAUTAMA PUTRA", "nik": "", "kk": "", "email": "", "hp": "", "alamat": "", "tempatLahir": "", "tglLahir": "", "joinDate": "2024-08-08", "jabatan": "Operator Warehouse", "departemen": "Warehouse Logistik", "atasan": "", "atasanId": "", "status": "AKTIF", "jadwalKerja": "SHIFT2", "jenisKontrak": "PKWT", "nomorKontrak": "KK-2408069", "kontrakMulai": "", "kontrakSelesai": ""}, {"id": "EMPX-065", "nama": "ABDUL RONY", "nik": "", "kk": "", "email": "", "hp": "", "alamat": "", "tempatLahir": "", "tglLahir": "", "joinDate": "2025-04-21", "jabatan": "Operator Warehouse", "departemen": "Warehouse Logistik", "atasan": "", "atasanId": "", "status": "AKTIF", "jadwalKerja": "SHIFT2", "jenisKontrak": "PKWT", "nomorKontrak": "KK-2504110", "kontrakMulai": "", "kontrakSelesai": ""}, {"id": "EMPX-066", "nama": "ABDUL HAMID", "nik": "3216010501910008", "kk": "", "email": "irmalisnawatidewiirma@gmail.com", "hp": "088298818792", "alamat": "Kp. Tanah Tinggi RT/002 RW/04 Setia Asih, Tarumajaya", "tempatLahir": "Bekasi", "tglLahir": "1993-02-08", "joinDate": "2018-02-19", "jabatan": "Maintenance", "departemen": "Warehouse RM", "atasan": "", "atasanId": "", "status": "AKTIF", "jadwalKerja": "STAFF", "jenisKontrak": "PKWT", "nomorKontrak": "KK-1802024", "kontrakMulai": "", "kontrakSelesai": ""}, {"id": "EMPX-067", "nama": "RACHMAT MARDIANTO", "nik": "3304011505910001", "kk": "", "email": "rahmatmas325@gmail.com", "hp": "085779759359", "alamat": "Dusun Pasirangin RT 01/05 Pasirangin, Cileungsi", "tempatLahir": "Banjarnegara", "tglLahir": "1991-05-15", "joinDate": "2015-01-15", "jabatan": "Maintenance", "departemen": "Warehouse RM", "atasan": "", "atasanId": "", "status": "AKTIF", "jadwalKerja": "STAFF", "jenisKontrak": "PKWT", "nomorKontrak": "KK-1501002", "kontrakMulai": "", "kontrakSelesai": ""}, {"id": "EMPX-068", "nama": "SUDARTO", "nik": "", "kk": "", "email": "", "hp": "", "alamat": "", "tempatLahir": "", "tglLahir": "", "joinDate": "2014-11-24", "jabatan": "Maintenance", "departemen": "Warehouse RM", "atasan": "", "atasanId": "", "status": "AKTIF", "jadwalKerja": "STAFF", "jenisKontrak": "PKWT", "nomorKontrak": "KK-1411001", "kontrakMulai": "", "kontrakSelesai": ""}, {"id": "EMPX-069", "nama": "IMAM MAHDI", "nik": "3216011210910002", "kk": "", "email": "imammahde9@gmail.com", "hp": "0895616003906", "alamat": "Kp. Bogor RT 01/10 Setia Asih, Tarumajaya", "tempatLahir": "Bekasi", "tglLahir": "1991-10-12", "joinDate": "2020-05-11", "jabatan": "Housekeeping", "departemen": "Housekeeping Produksi", "atasan": "", "atasanId": "", "status": "AKTIF", "jadwalKerja": "STAFF", "jenisKontrak": "PKWT", "nomorKontrak": "KK-2005041", "kontrakMulai": "", "kontrakSelesai": ""}, {"id": "EMPX-070", "nama": "MUKMININ", "nik": "3216011501890002", "kk": "", "email": "mukmininmukmininpanjoel@gmail.com", "hp": "088808306244", "alamat": "Kp. Penggarutan RT 02/06", "tempatLahir": "Bekasi", "tglLahir": "1989-01-15", "joinDate": "2020-06-19", "jabatan": "Housekeeping", "departemen": "Housekeeping Produksi", "atasan": "", "atasanId": "", "status": "AKTIF", "jadwalKerja": "STAFF", "jenisKontrak": "PKWT", "nomorKontrak": "KK-2006043", "kontrakMulai": "", "kontrakSelesai": ""}, {"id": "EMPX-071", "nama": "ALDI MAULANA", "nik": "3216072103960003", "kk": "", "email": "aldym243@gmail.com", "hp": "085776661989", "alamat": "Kp. Tanah Tinggi RT 02/05 Setia Asih, Tarumajaya", "tempatLahir": "Bekasi", "tglLahir": "1996-03-21", "joinDate": "2022-11-18", "jabatan": "Housekeeping", "departemen": "Housekeeping Produksi", "atasan": "", "atasanId": "", "status": "AKTIF", "jadwalKerja": "STAFF", "jenisKontrak": "Harian", "nomorKontrak": "KH-2211007", "kontrakMulai": "", "kontrakSelesai": ""}, {"id": "EMPX-072", "nama": "ALAN KURNIA", "nik": "3275012104920012", "kk": "", "email": "alankurnia241@gmail.com", "hp": "0895332739067", "alamat": "Kp. Rawa Aren RT 03/02 Aren Jaya, Bekasi Timur", "tempatLahir": "Bekasi", "tglLahir": "1992-04-21", "joinDate": "2023-03-02", "jabatan": "Housekeeping", "departemen": "Housekeeping Produksi", "atasan": "", "atasanId": "", "status": "AKTIF", "jadwalKerja": "STAFF", "jenisKontrak": "Harian", "nomorKontrak": "KH-2303024", "kontrakMulai": "", "kontrakSelesai": ""}, {"id": "EMPX-073", "nama": "TAUFIK HIDAYAT", "nik": "", "kk": "", "email": "", "hp": "", "alamat": "", "tempatLahir": "", "tglLahir": "", "joinDate": "2025-02-07", "jabatan": "Housekeeping", "departemen": "Housekeeping Produksi", "atasan": "", "atasanId": "", "status": "AKTIF", "jadwalKerja": "STAFF", "jenisKontrak": "Harian", "nomorKontrak": "KH-2502045", "kontrakMulai": "", "kontrakSelesai": ""}, {"id": "EMPX-074", "nama": "AZRIL", "nik": "3216011912040002", "kk": "", "email": "ratuzahrotunnurussyita@gmail.com", "hp": "083807655372", "alamat": "Kp. Tanah Tinggi RT 02/04 Setia Asih, Tarumajaya", "tempatLahir": "Bekasi", "tglLahir": "2004-12-19", "joinDate": "2023-03-02", "jabatan": "Housekeeping", "departemen": "Housekeeping Produksi", "atasan": "", "atasanId": "", "status": "AKTIF", "jadwalKerja": "STAFF", "jenisKontrak": "Harian", "nomorKontrak": "KH-2303025", "kontrakMulai": "", "kontrakSelesai": ""}, {"id": "EMPX-075", "nama": "JAINUDIN", "nik": "3216011508030006", "kk": "", "email": "jainudinjejem9@gmail.com", "hp": "08388599726", "alamat": "Kp. Tambun Semer RT 01/03 Pahlawan Setia, Tarumajaya", "tempatLahir": "Bekasi", "tglLahir": "2003-08-15", "joinDate": "2022-12-12", "jabatan": "Housekeeping", "departemen": "Housekeeping Produksi", "atasan": "", "atasanId": "", "status": "AKTIF", "jadwalKerja": "STAFF", "jenisKontrak": "Harian", "nomorKontrak": "KH-2212017", "kontrakMulai": "", "kontrakSelesai": ""}, {"id": "EMPX-076", "nama": "IRHAM SODRY", "nik": "", "kk": "", "email": "", "hp": "", "alamat": "", "tempatLahir": "", "tglLahir": "", "joinDate": "2025-01-20", "jabatan": "Housekeeping", "departemen": "Housekeeping Produksi", "atasan": "", "atasanId": "", "status": "AKTIF", "jadwalKerja": "STAFF", "jenisKontrak": "Harian", "nomorKontrak": "KH-2501044", "kontrakMulai": "", "kontrakSelesai": ""}, {"id": "EMPX-077", "nama": "ABDUL HALIM", "nik": "", "kk": "", "email": "", "hp": "", "alamat": "", "tempatLahir": "", "tglLahir": "", "joinDate": "", "jabatan": "Housekeeping", "departemen": "Housekeeping Produksi", "atasan": "", "atasanId": "", "status": "AKTIF", "jadwalKerja": "STAFF", "jenisKontrak": "Harian", "nomorKontrak": "KH-2503053", "kontrakMulai": "", "kontrakSelesai": ""}, {"id": "EMPX-078", "nama": "SUNARYA", "nik": "3216020805950003", "kk": "", "email": "sunaryanembre@gmail.com", "hp": "0895331494970", "alamat": "Kp. Cabang Empat RT 02/01 Hurip Jaya, Babelan", "tempatLahir": "Bekasi", "tglLahir": "1995-05-08", "joinDate": "2022-11-16", "jabatan": "Housekeeping", "departemen": "Office Boy", "atasan": "", "atasanId": "", "status": "AKTIF", "jadwalKerja": "STAFF", "jenisKontrak": "Harian", "nomorKontrak": "KK-221122", "kontrakMulai": "", "kontrakSelesai": ""}, {"id": "EMPX-079", "nama": "TOHA", "nik": "3216010308870005", "kk": "", "email": "toha34241@gmail.com", "hp": "0895615761431", "alamat": "Kp. Tambun Semer RT 01/03 Pahlawan Setia, Tarumajaya", "tempatLahir": "Bekasi", "tglLahir": "1987-08-03", "joinDate": "2019-01-09", "jabatan": "Security", "departemen": "Security", "atasan": "", "atasanId": "", "status": "AKTIF", "jadwalKerja": "STAFF", "jenisKontrak": "PKWT", "nomorKontrak": "KK-1901034", "kontrakMulai": "", "kontrakSelesai": ""}, {"id": "EMPX-080", "nama": "SARMILIH", "nik": "3216011206660005", "kk": "", "email": "sarmilihaja56@gmail.com", "hp": "081294618352", "alamat": "Kp. Pulo Kendal RT 001/003 Setia Asih, Tarumajaya", "tempatLahir": "Bekasi", "tglLahir": "1966-06-12", "joinDate": "2019-01-02", "jabatan": "Security", "departemen": "Security", "atasan": "", "atasanId": "", "status": "AKTIF", "jadwalKerja": "STAFF", "jenisKontrak": "PKWT", "nomorKontrak": "KK-1901032", "kontrakMulai": "", "kontrakSelesai": ""}, {"id": "EMPX-081", "nama": "KARMAN PERMANA", "nik": "3216152105780003", "kk": "", "email": "karmanpermana@gmail.com", "hp": "085975245297", "alamat": "Kp. Srengseng RT 03/05 Sukamulya, Sukatani", "tempatLahir": "Bekasi", "tglLahir": "1978-05-21", "joinDate": "2021-04-01", "jabatan": "Security", "departemen": "Security", "atasan": "", "atasanId": "", "status": "AKTIF", "jadwalKerja": "STAFF", "jenisKontrak": "PKWT", "nomorKontrak": "KK-2104054", "kontrakMulai": "", "kontrakSelesai": ""}, {"id": "EMPX-082", "nama": "FEBRI MARIYATNA", "nik": "", "kk": "", "email": "", "hp": "", "alamat": "", "tempatLahir": "", "tglLahir": "", "joinDate": "2025-01-06", "jabatan": "Security", "departemen": "Security", "atasan": "", "atasanId": "", "status": "AKTIF", "jadwalKerja": "STAFF", "jenisKontrak": "PKWT", "nomorKontrak": "KK-2501077", "kontrakMulai": "", "kontrakSelesai": ""}, {"id": "EMPX-083", "nama": "AHMAD NURFAHREZA", "nik": "", "kk": "", "email": "", "hp": "", "alamat": "", "tempatLahir": "", "tglLahir": "", "joinDate": "", "jabatan": "Security", "departemen": "Security", "atasan": "", "atasanId": "", "status": "AKTIF", "jadwalKerja": "STAFF", "jenisKontrak": "PKWT", "nomorKontrak": "", "kontrakMulai": "", "kontrakSelesai": ""}, {"id": "EMPX-084", "nama": "ARI SUDARSONO", "nik": "3275062401850011", "kk": "", "email": "", "hp": "081290437075", "alamat": "Pejuang Jaya Blok A No. 212 RT 04/011 Pejuang, Medan Satria", "tempatLahir": "Purworejo", "tglLahir": "1985-01-24", "joinDate": "2014-01-02", "jabatan": "Direktur", "departemen": "Direktur Utama", "atasan": "", "atasanId": "", "status": "AKTIF", "jadwalKerja": "STAFF", "jenisKontrak": "Tetap", "nomorKontrak": "KT-1401001", "kontrakMulai": "", "kontrakSelesai": ""}, {"id": "EMPX-085", "nama": "TRI AHMAD", "nik": "3306081101960001", "kk": "", "email": "produksi.rajaroti.ho@gmail.com", "hp": "081382849509", "alamat": "Desa Bayan RT 02/01 Bayan, Purworejo", "tempatLahir": "Purworejo", "tglLahir": "1996-01-11", "joinDate": "2019-01-11", "jabatan": "Maintenance & Produksi", "departemen": "MTC", "atasan": "", "atasanId": "", "status": "AKTIF", "jadwalKerja": "STAFF", "jenisKontrak": "Tetap", "nomorKontrak": "KT-1901007", "kontrakMulai": "", "kontrakSelesai": ""}, {"id": "EMPX-086", "nama": "ANA LUSTIANA", "nik": "3275045102960005", "kk": "", "email": "ana.lustiana@gmail.com", "hp": "085692532490", "alamat": "Jl Veteran Gg H.Ukar AB Rt.01 Rw.03 No 49 , Margajaya, Bekasi Selatan", "tempatLahir": "Bekasi", "tglLahir": "1996-02-11", "joinDate": "2018-05-14", "jabatan": "Admin Sales", "departemen": "Sales", "atasan": "", "atasanId": "", "status": "AKTIF", "jadwalKerja": "STAFF", "jenisKontrak": "Tetap", "nomorKontrak": "KT-1805005", "kontrakMulai": "", "kontrakSelesai": ""}, {"id": "EMPX-087", "nama": "NUR AZIZA HANIFA", "nik": "3275115112990004", "kk": "", "email": "azizahanifa.ah@gmail.com", "hp": "082113370814", "alamat": "Perum. Dukuh Zamrud Blok Q 04/03 RT 004/013 Padurenan, Mustikajaya", "tempatLahir": "Jakarta", "tglLahir": "1999-12-11", "joinDate": "2017-07-10", "jabatan": "Staff HR", "departemen": "HR", "atasan": "", "atasanId": "", "status": "AKTIF", "jadwalKerja": "STAFF", "jenisKontrak": "Tetap", "nomorKontrak": "KT-1707004", "kontrakMulai": "", "kontrakSelesai": ""}, {"id": "EMPX-088", "nama": "NURAINI EKA", "nik": "3275067101000015", "kk": "", "email": "nurainieka396@gmail.com", "hp": "085776420135", "alamat": "Klapasawit RT 02/03 Candiwulan, Adimulyo", "tempatLahir": "Bekasi", "tglLahir": "2000-01-31", "joinDate": "2015-11-26", "jabatan": "Staff Warehouse", "departemen": "Warehouse", "atasan": "", "atasanId": "", "status": "AKTIF", "jadwalKerja": "STAFF", "jenisKontrak": "Tetap", "nomorKontrak": "KT-1511002", "kontrakMulai": "", "kontrakSelesai": ""}, {"id": "EMPX-089", "nama": "TANNIA MEGA FERNANDA", "nik": "3402144109960005", "kk": "", "email": "tanniamf.tm@gmail.com", "hp": "082123017123", "alamat": "Kp. Buaran RT 02/14 Cikokol, Tangerang, Banten", "tempatLahir": "Rangkasbitung", "tglLahir": "1996-09-01", "joinDate": "2021-02-22", "jabatan": "Manager QAQC&PD", "departemen": "QAQC&PD", "atasan": "", "atasanId": "", "status": "AKTIF", "jadwalKerja": "STAFF", "jenisKontrak": "Tetap", "nomorKontrak": "", "kontrakMulai": "", "kontrakSelesai": ""}, {"id": "EMPX-090", "nama": "TENGKU AMIRA", "nik": "3216066006960024", "kk": "", "email": "tengkuamira29@gmail.com", "hp": "089692760420", "alamat": "Kp. Rawa Sapi RT 02/10 Jatimulya, Tambun Selatan", "tempatLahir": "Bekasi", "tglLahir": "1996-06-29", "joinDate": "2021-01-21", "jabatan": "Spv Purchasing", "departemen": "Purchasing", "atasan": "", "atasanId": "", "status": "AKTIF", "jadwalKerja": "STAFF", "jenisKontrak": "Tetap", "nomorKontrak": "KT-2101008", "kontrakMulai": "", "kontrakSelesai": ""}, {"id": "EMPX-091", "nama": "NURJIHAN KHAIRUNISA", "nik": "3216016604970005", "kk": "", "email": "hinurjihan@gmail.com", "hp": "085773950001", "alamat": "Puri Harapan Blok C17/34 RT 001/017 Setia Asih, Tarumajaya", "tempatLahir": "Jakarta", "tglLahir": "1997-04-26", "joinDate": "2024-01-13", "jabatan": "Corsec", "departemen": "Corsec", "atasan": "", "atasanId": "", "status": "AKTIF", "jadwalKerja": "STAFF", "jenisKontrak": "Tetap", "nomorKontrak": "KT-2401014", "kontrakMulai": "", "kontrakSelesai": ""}, {"id": "EMPX-092", "nama": "ANISYA REPIKA SARI", "nik": "", "kk": "", "email": "", "hp": "", "alamat": "", "tempatLahir": "", "tglLahir": "", "joinDate": "2024-08-05", "jabatan": "Spv QC", "departemen": "QAQC&PD", "atasan": "", "atasanId": "", "status": "AKTIF", "jadwalKerja": "STAFF", "jenisKontrak": "Tetap", "nomorKontrak": "", "kontrakMulai": "", "kontrakSelesai": ""}, {"id": "EMPX-093", "nama": "NINIK MUNDARSIH", "nik": "", "kk": "", "email": "", "hp": "", "alamat": "", "tempatLahir": "", "tglLahir": "", "joinDate": "2025-05-02", "jabatan": "Spv RnD", "departemen": "QAQC&PD", "atasan": "", "atasanId": "", "status": "AKTIF", "jadwalKerja": "STAFF", "jenisKontrak": "Tetap", "nomorKontrak": "KK-2505090", "kontrakMulai": "", "kontrakSelesai": ""}, {"id": "EMPX-094", "nama": "AISHA APRILIA", "nik": "", "kk": "", "email": "", "hp": "", "alamat": "", "tempatLahir": "", "tglLahir": "", "joinDate": "2025-06-24", "jabatan": "Admin Produksi", "departemen": "Produksi", "atasan": "", "atasanId": "", "status": "AKTIF", "jadwalKerja": "STAFF", "jenisKontrak": "Tetap", "nomorKontrak": "KK-2506094", "kontrakMulai": "", "kontrakSelesai": ""}, {"id": "EMPX-095", "nama": "FEMY FATUROHMAH", "nik": "", "kk": "", "email": "", "hp": "", "alamat": "", "tempatLahir": "", "tglLahir": "", "joinDate": "2025-04-07", "jabatan": "Staff QA", "departemen": "QAQC&PD", "atasan": "", "atasanId": "", "status": "AKTIF", "jadwalKerja": "STAFF", "jenisKontrak": "PKWT", "nomorKontrak": "KK-2504088", "kontrakMulai": "", "kontrakSelesai": ""}, {"id": "EMPX-096", "nama": "ARI DWI HERAWAN", "nik": "", "kk": "", "email": "", "hp": "", "alamat": "", "tempatLahir": "", "tglLahir": "", "joinDate": "", "jabatan": "Manager FAT", "departemen": "FAT", "atasan": "", "atasanId": "", "status": "AKTIF", "jadwalKerja": "STAFF", "jenisKontrak": "PKWT", "nomorKontrak": "", "kontrakMulai": "", "kontrakSelesai": ""}, {"id": "EMPX-097", "nama": "HAWARI ROSDIANA MAHMUDA", "nik": "", "kk": "", "email": "", "hp": "", "alamat": "", "tempatLahir": "", "tglLahir": "", "joinDate": "2025-09-22", "jabatan": "QC Lab Mikro", "departemen": "QAQC&PD", "atasan": "", "atasanId": "", "status": "AKTIF", "jadwalKerja": "STAFF", "jenisKontrak": "PKWT", "nomorKontrak": "KK-2509104", "kontrakMulai": "", "kontrakSelesai": ""}, {"id": "EMPX-098", "nama": "FADILAH FITRI AISYAH", "nik": "", "kk": "", "email": "", "hp": "", "alamat": "", "tempatLahir": "", "tglLahir": "", "joinDate": "2025-12-03", "jabatan": "Staff Acc & Tax", "departemen": "FAT", "atasan": "", "atasanId": "", "status": "AKTIF", "jadwalKerja": "STAFF", "jenisKontrak": "PKWT", "nomorKontrak": "", "kontrakMulai": "", "kontrakSelesai": ""}, {"id": "EMPX-099", "nama": "IRNANDA UMMI", "nik": "", "kk": "", "email": "", "hp": "", "alamat": "", "tempatLahir": "", "tglLahir": "", "joinDate": "2026-01-05", "jabatan": "Ass R&D", "departemen": "QAQC&PD", "atasan": "", "atasanId": "", "status": "AKTIF", "jadwalKerja": "STAFF", "jenisKontrak": "PKWT", "nomorKontrak": "KK-2601118", "kontrakMulai": "", "kontrakSelesai": ""}, {"id": "EMPX-100", "nama": "INDRO SURYO", "nik": "", "kk": "", "email": "", "hp": "", "alamat": "", "tempatLahir": "", "tglLahir": "", "joinDate": "2026-01-20", "jabatan": "Manager Operasional", "departemen": "Operasional", "atasan": "", "atasanId": "", "status": "AKTIF", "jadwalKerja": "STAFF", "jenisKontrak": "PKWT", "nomorKontrak": "KK-2601119", "kontrakMulai": "", "kontrakSelesai": ""}, {"id": "EMPX-101", "nama": "ADINDA RAHMAYANTI LUKMAN", "nik": "", "kk": "", "email": "", "hp": "", "alamat": "", "tempatLahir": "", "tglLahir": "", "joinDate": "2026-02-04", "jabatan": "Staff Finance", "departemen": "FAT", "atasan": "", "atasanId": "", "status": "AKTIF", "jadwalKerja": "STAFF", "jenisKontrak": "PKWT", "nomorKontrak": "KK-2602122", "kontrakMulai": "", "kontrakSelesai": ""}, {"id": "EMPX-102", "nama": "ANGGA DWI ANANDA PUTRA", "nik": "", "kk": "", "email": "", "hp": "", "alamat": "", "tempatLahir": "", "tglLahir": "", "joinDate": "", "jabatan": "Staff HRGA", "departemen": "HRGA", "atasan": "", "atasanId": "", "status": "AKTIF", "jadwalKerja": "STAFF", "jenisKontrak": "PKWT", "nomorKontrak": "", "kontrakMulai": "", "kontrakSelesai": ""}, {"id": "EMPX-103", "nama": "Muhammad Helmi Athallah", "nik": "3276052708020000", "kk": "", "email": "helmiathallah123@gmail.com", "hp": "085163561301", "alamat": "Perum Cening Ampe Blok G no 2 RT 02 RW 027 kelurahan sukamaju Kecamatan Cilodong Kota depok", "tempatLahir": "Depok", "tglLahir": "2002-08-27", "joinDate": "2026-09-07", "jabatan": "Staff HRGA", "departemen": "HRGA", "atasan": "", "atasanId": "", "status": "AKTIF", "jadwalKerja": "STAFF", "jenisKontrak": "Probation", "nomorKontrak": "", "kontrakMulai": "", "kontrakSelesai": ""}];
function departemenOptionsHtml(selected){
  return DEPARTEMEN_GROUPS.map(g => `<optgroup label="${escapeHtml(g.grup)}">${
    g.items.map(d => `<option value="${escapeHtml(d)}" ${selected===d?'selected':''}>${escapeHtml(d)}</option>`).join('')
  }</optgroup>`).join('');
}
function todayISO(){ return new Date().toISOString().slice(0,10); }
function nowTimeStr(){
  const d = new Date();
  return String(d.getHours()).padStart(2,'0') + ':' + String(d.getMinutes()).padStart(2,'0');
}
function fmtDate(iso){
  if(!iso) return '-';
  const d = new Date(iso + 'T00:00:00');
  const bulan = ['Jan','Feb','Mar','Apr','Mei','Jun','Jul','Agu','Sep','Okt','Nov','Des'];
  return d.getDate() + ' ' + bulan[d.getMonth()] + ' ' + d.getFullYear();
}
function fmtDateTime(ts){
  if(!ts) return '-';
  const d = new Date(ts);
  return fmtDate(d.toISOString().slice(0,10)) + ', ' + String(d.getHours()).padStart(2,'0') + ':' + String(d.getMinutes()).padStart(2,'0');
}
function escapeHtml(str){
  if(str === undefined || str === null) return '';
  return String(str).replace(/[&<>"']/g, s => ({'&':'&amp;','<':'&lt;','>':'&gt;','"':'&quot;',"'":'&#39;'}[s]));
}
function daysBetween(dateISOa, dateISOb){
  const a = new Date(dateISOa + 'T00:00:00');
  const b = new Date(dateISOb + 'T00:00:00');
  return Math.round((b - a) / 86400000);
}
function toast(message, type){
  const wrap = document.getElementById('toastWrap');
  const el = document.createElement('div');
  el.className = 'toast' + (type ? ' ' + type : '');
  el.textContent = message;
  wrap.appendChild(el);
  setTimeout(()=>{ el.style.transition='opacity .3s'; el.style.opacity='0'; setTimeout(()=>el.remove(),300); }, 3200);
}

/* Haversine distance in meters between two lat/lng points */
function haversineDistance(lat1, lon1, lat2, lon2){
  const R = 6371000;
  const toRad = d => d * Math.PI / 180;
  const dLat = toRad(lat2 - lat1);
  const dLon = toRad(lon2 - lon1);
  const a = Math.sin(dLat/2) ** 2 + Math.cos(toRad(lat1)) * Math.cos(toRad(lat2)) * Math.sin(dLon/2) ** 2;
  const c = 2 * Math.atan2(Math.sqrt(a), Math.sqrt(1 - a));
  return R * c;
}

/* ---------------------------------------------------------------------
   4. AUTH
--------------------------------------------------------------------- */
function currentUser(){
  const id = sessionStorage.getItem(DB_PREFIX + 'session');
  if(!id) return null;
  const u = DB.users().find(x => x.id === id && x.active !== false);
  return u || null;
}
function login(email, password){
  const u = DB.users().find(x => x.email.toLowerCase() === String(email).toLowerCase() && String(x.password) === String(password));
  if(!u) return {ok:false, message:'Email atau password salah.'};
  if(u.active === false) return {ok:false, message:'Akun tidak aktif. Hubungi HRD.'};
  sessionStorage.setItem(DB_PREFIX + 'session', u.id);
  writeAudit(u, 'Login ke sistem', u.email, '-', '-');
  return {ok:true, user:u};
}
function logout(){
  const u = currentUser();
  if(u) writeAudit(u, 'Logout dari sistem', u.email, '-', '-');
  sessionStorage.removeItem(DB_PREFIX + 'session');
}
/* Authoritative role guard used inside EVERY sensitive/mutating function.
   This is re-checked from storage every call - never trusted from a
   variable held in the UI layer - so a user cannot bypass it by calling
   a function directly from the console or by hiding/showing buttons. */
function requireRole(role){
  const u = currentUser();
  if(!u || u.role !== role){
    writeAudit(u || {email:'UNKNOWN'}, 'PERCOBAAN AKSES DITOLAK (butuh role ' + role + ')', '-', '-', '-');
    throw new Error('Akses ditolak: aksi ini hanya untuk role ' + role + '.');
  }
  return u;
}
function getEmployeeByUserId(userId){
  const u = DB.users().find(x => x.id === userId);
  if(!u) return null;
  return DB.employees().find(e => e.id === u.employeeId) || null;
}
function getEmployeeForCurrentUser(){
  const u = currentUser();
  if(!u) return null;
  return getEmployeeByUserId(u.id);
}

/* ---------------------------------------------------------------------
   5. AUDIT LOG (append-only - no delete function exists anywhere)
--------------------------------------------------------------------- */
function writeAudit(user, aktivitas, data, statusSebelum, statusSesudah){
  const logs = DB.auditLogs();
  logs.unshift({
    id: uid('LOG'),
    user: (user && user.email) || 'SYSTEM',
    role: (user && user.role) || '-',
    aktivitas,
    data: data || '-',
    waktu: Date.now(),
    statusSebelum: statusSebelum || '-',
    statusSesudah: statusSesudah || '-'
  });
  DB.set('auditLogs', logs);
}

/* ---------------------------------------------------------------------
   6. NOTIFICATIONS
--------------------------------------------------------------------- */
function pushNotification(targetEmployeeId, targetRole, message){
  const list = DB.notifications();
  list.unshift({
    id: uid('NTF'),
    employeeId: targetEmployeeId || null,
    role: targetRole || null,
    message,
    read: false,
    createdAt: Date.now()
  });
  DB.set('notifications', list);
}
function myNotifications(){
  const u = currentUser();
  if(!u) return [];
  const emp = getEmployeeByUserId(u.id);
  return DB.notifications().filter(n => (n.employeeId && emp && n.employeeId === emp.id) || (n.role && n.role === u.role))
    .sort((a,b)=>b.createdAt-a.createdAt);
}

/* ---------------------------------------------------------------------
   7. GPS ATTENDANCE
--------------------------------------------------------------------- */
const GPS_ACCURACY_LIMIT = 150; // meters - beyond this we ask the user to retry, we never hard-fail permanently
const GPS_SAMPLES = 2;

function getBestPosition(samples){
  samples = samples || GPS_SAMPLES;
  return new Promise((resolve, reject) => {
    if(!('geolocation' in navigator)){
      reject(new Error('Perangkat/browser ini tidak mendukung GPS.'));
      return;
    }
    const results = [];
    let attempts = 0;
    function attempt(){
      navigator.geolocation.getCurrentPosition(
        pos => {
          results.push(pos);
          attempts++;
          if(attempts >= samples){
            results.sort((a,b) => a.coords.accuracy - b.coords.accuracy);
            resolve(results[0]);
          } else {
            attempt();
          }
        },
        err => {
          if(results.length > 0){
            results.sort((a,b) => a.coords.accuracy - b.coords.accuracy);
            resolve(results[0]);
          } else {
            reject(err);
          }
        },
        { enableHighAccuracy: true, maximumAge: 0, timeout: 12000 }
      );
    }
    attempt();
  });
}

/* ---------------------------------------------------------------------
   MASTER JADWAL KERJA (dinamis, bisa ditambah/edit HRD tanpa ubah kode)
--------------------------------------------------------------------- */
function jadwalKerjaList(){ return DB.jadwalKerja(); }
function findJadwal(kode){ return jadwalKerjaList().find(j => j.kode === kode); }
function jadwalOptionsHtml(selected){
  return jadwalKerjaList().map(j => `<option value="${escapeHtml(j.kode)}" ${selected===j.kode?'selected':''}>${escapeHtml(j.nama)}</option>`).join('');
}
// Karyawan lama masih punya field 'shift' (versi sebelumnya) - tetap dianggap valid.
function getJadwalKerjaKode(emp){
  return (emp && (emp.jadwalKerja || emp.shift)) || 'STAFF';
}
// Untuk jadwal yang ikut Roster Shift Mingguan (SHIFT1/2/3), cek dulu apa ada
// entri roster di tanggal itu; kalau tidak ada, pakai jadwal default karyawan.
function getEffectiveJadwalKode(emp, tanggalISO){
  const baseKode = getJadwalKerjaKode(emp);
  const baseDef = findJadwal(baseKode);
  if(baseDef && baseDef.bisaRoster){
    const roster = DB.rosterShift().find(r => r.employeeId === emp.id && r.tanggal === tanggalISO);
    if(roster && roster.shiftKode) return roster.shiftKode;
  }
  return baseKode;
}
function timeToMinutes(t){ const p = String(t||'0:0').split(':'); return (+p[0])*60 + (+p[1]); }
// Cari jam kerja yang berlaku buat karyawan itu di tanggal tertentu, termasuk
// aturan khusus Sabtu untuk jadwal STAFF, dan libur hari Minggu.
// Balikin null kalau hari itu memang bukan hari kerja (libur).
function getJamKerjaForDate(emp, tanggalISO){
  const kode = getEffectiveJadwalKode(emp, tanggalISO);
  const def = findJadwal(kode) || findJadwal('STAFF');
  if(!def) return null;
  const day = new Date(tanggalISO + 'T00:00:00').getDay(); // 0=Minggu ... 6=Sabtu
  if(day === 0 && !def.kerjaMinggu) return null;
  if(day === 6){
    if(def.jamMasukSabtu) return { jamMasuk: def.jamMasukSabtu, jamPulang: def.jamPulangSabtu, overnight:false, kode, nama: def.nama };
    if(!def.kerjaSabtu) return null;
  }
  return { jamMasuk: def.jamMasuk, jamPulang: def.jamPulang, overnight: !!def.overnight, kode, nama: def.nama };
}
// Kalau jadwal hari ini overnight (mis. Shift 1: 23:00-07:00), absen jam
// 00:00-11:59 dianggap masih bagian dari shift yang DIMULAI kemarin.
function shiftAttendanceDate(emp){
  const kodeHariIni = getEffectiveJadwalKode(emp, todayISO());
  const defHariIni = findJadwal(kodeHariIni);
  if(defHariIni && defHariIni.overnight && new Date().getHours() < 12){
    return new Date(Date.now() - 24*60*60*1000).toISOString().slice(0,10);
  }
  return todayISO();
}
function jamKerjaFor(emp, officeSettings){
  const jk = getJamKerjaForDate(emp, shiftAttendanceDate(emp));
  if(jk) return jk;
  return { jamMasuk: officeSettings.jamMasuk, jamPulang: officeSettings.jamPulang, overnight:false, kode:'LIBUR', nama:'Libur' };
}
function saveJadwalKerja(payload, editKode){
  const hrd = requireRole('HRD');
  const list = jadwalKerjaList();
  if(editKode){
    const idx = list.findIndex(j => j.kode === editKode);
    if(idx === -1) throw new Error('Jadwal tidak ditemukan.');
    list[idx] = Object.assign({}, list[idx], payload);
  }else{
    if(list.find(j => j.kode === payload.kode)) throw new Error('Kode jadwal sudah dipakai.');
    list.push(payload);
  }
  DB.set('jadwalKerja', list);
  writeAudit(hrd, editKode?'Mengubah jadwal kerja':'Menambah jadwal kerja', payload.kode, '-', 'tersimpan');
}
function deleteJadwalKerja(kode){
  const hrd = requireRole('HRD');
  if(kode === 'STAFF') throw new Error('Jadwal STAFF tidak bisa dihapus.');
  DB.set('jadwalKerja', jadwalKerjaList().filter(j => j.kode !== kode));
  writeAudit(hrd, 'Menghapus jadwal kerja', kode, '-', 'dihapus');
}
function saveRosterShift(entries){
  // entries: [{employeeId, nama, tanggal, shiftKode}], shiftKode '' berarti hapus entri (pakai default)
  const hrd = requireRole('HRD');
  let list = DB.rosterShift();
  entries.forEach(e => {
    list = list.filter(r => !(r.employeeId === e.employeeId && r.tanggal === e.tanggal));
    if(e.shiftKode) list.push({ id: uid('ROS'), employeeId: e.employeeId, nama: e.nama, tanggal: e.tanggal, shiftKode: e.shiftKode });
  });
  DB.set('rosterShift', list);
  writeAudit(hrd, 'Menyimpan roster shift mingguan', entries.length + ' entri', '-', 'tersimpan');
}

/* ---------------------------------------------------------------------
   DETEKSI ALPHA (Pasal 5 Ayat 1-2)
   Dijalankan sekali per sesi HRD (lihat UI.alphaChecked) - menandai hari
   kerja yang terlewat tanpa absen masuk & tanpa cuti/izin disetujui.
--------------------------------------------------------------------- */
const ALPHA_LOOKBACK_DAYS = 62; // dibatasi ~2 bulan terakhir biar scan tidak berat
function detectAndMarkAlpha(onDone){
  const hrd = currentUser();
  if(!hrd || hrd.role !== 'HRD'){ onDone && onDone(0); return; }
  const employees = DB.employees().filter(e => e.status === 'AKTIF');
  const attendance = DB.attendance();
  if(attendance.length > 8000){
    // Pengaman: kalau data absensi sudah kelewat banyak (indikasi ada yang perlu dibersihkan manual),
    // jangan paksa proses otomatis di browser - lebih baik berhenti daripada bikin berat.
    onDone && onDone(0);
    return;
  }
  const yesterday = addDaysStr(todayISO(), -1);
  const settings = DB.officeSettings();
  const earliestGlobal = addDaysStr(todayISO(), -ALPHA_LOOKBACK_DAYS);
  // Tidak pernah mundur melewati tanggal sistem ini benar-benar mulai dipakai,
  // meskipun karyawan sudah join lama sebelumnya atau lookback masih mengizinkan.
  const earliestAllowed = (settings && settings.tanggalMulaiAbsensi && settings.tanggalMulaiAbsensi > earliestGlobal)
    ? settings.tanggalMulaiAbsensi : earliestGlobal;

  const attendanceKeys = new Set(attendance.map(a => a.employeeId + '|' + a.tanggal));
  const coveredKeys = new Set();
  DB.leaveRequests().forEach(r => {
    if(r.status !== 'DISETUJUI') return;
    let d = r.tglMulai;
    let guard = 0;
    while(d <= r.tglSelesai && guard < 400){ coveredKeys.add(r.employeeId + '|' + d); d = addDaysStr(d, 1); guard++; }
  });
  DB.permissionRequests().forEach(r => {
    if(r.status === 'DISETUJUI') coveredKeys.add(r.employeeId + '|' + r.tanggal);
  });

  const newRecords = [];
  let idx = 0;
  // Diproses 2 karyawan per "tick" (setTimeout) supaya main thread browser tidak pernah
  // diblokir lama dalam satu waktu, berapa pun banyaknya data yang sudah menumpuk.
  function processNext(){
    const batchEnd = Math.min(idx + 2, employees.length);
    for(; idx < batchEnd; idx++){
      const emp = employees[idx];
      let d = (emp.joinDate && emp.joinDate > earliestAllowed) ? emp.joinDate : earliestAllowed;
      let guard = 0;
      while(d <= yesterday && guard < ALPHA_LOOKBACK_DAYS + 1){
        const key = emp.id + '|' + d;
        if(!attendanceKeys.has(key) && !coveredKeys.has(key)){
          const jamKerja = getJamKerjaForDate(emp, d);
          if(jamKerja){
            newRecords.push({
              id: uid('ATT'), employeeId: emp.id, nama: emp.nama, tanggal: d, shift: jamKerja.kode || '',
              jamMasuk:'', jamPulang:'', latMasuk:null, lngMasuk:null, accMasuk:null, jarakMasuk:null,
              latPulang:null, lngPulang:null, accPulang:null, jarakPulang:null,
              statusMasuk:'ALPHA', userAgent:'system', timestampMasuk:null, timestampPulang:null
            });
          }
        }
        d = addDaysStr(d, 1);
        guard++;
      }
    }
    if(idx < employees.length){
      setTimeout(processNext, 0);
    }else{
      if(newRecords.length){
        DB.set('attendance', attendance.concat(newRecords));
        writeAudit(hrd, 'Deteksi otomatis Alpha', newRecords.length + ' record baru', '-', 'ALPHA');
      }
      onDone && onDone(newRecords.length);
    }
  }
  processNext();
}

/* ---------------------------------------------------------------------
   PAYROLL (gaji pokok+tunjangan, lembur, potongan telat, BPJS TK, PPh21)
   Catatan: PPh 21 dihitung pakai metode progresif tahunan yang
   disederhanakan (bukan tabel TER bulanan resmi terbaru) - cukup untuk
   estimasi, sebaiknya tetap dicek ulang oleh HRD/akuntan sebelum dipakai
   sebagai angka final pembayaran gaji.
--------------------------------------------------------------------- */
const PTKP_OPTIONS = ['TK0','TK1','TK2','TK3','K0','K1','K2','K3'];
function ptkpLabel(kode){
  if(!kode) return 'TK/0';
  return kode.slice(0,2) + '/' + kode.slice(2);
}
function ptkpAnnual(kode){
  const k = kode || 'TK0';
  const base = 54000000;
  const kawin = k.charAt(0) === 'K' ? 4500000 : 0;
  const tanggungan = (parseInt(k.slice(-1), 10) || 0) * 4500000;
  return base + kawin + tanggungan;
}
function hitungPPh21Tahunan(pkp){
  if(pkp <= 0) return 0;
  const brackets = [[60000000,0.05],[250000000,0.15],[500000000,0.25],[5000000000,0.30],[Infinity,0.35]];
  let sisa = pkp, pajak = 0, batasBawah = 0;
  for(const [batasAtas, tarif] of brackets){
    if(sisa <= 0) break;
    const kena = Math.min(sisa, batasAtas - batasBawah);
    pajak += kena * tarif;
    sisa -= kena;
    batasBawah = batasAtas;
  }
  return pajak;
}
function hitungPPh21Bulanan(brutoBulanan, ptkpKode, bpjsKaryawanBulanan){
  const brutoTahunan = brutoBulanan * 12;
  const biayaJabatanTahunan = Math.min(brutoBulanan * 0.05, 500000) * 12;
  const neto = brutoTahunan - biayaJabatanTahunan - (bpjsKaryawanBulanan * 12);
  const pkp = Math.max(0, Math.floor((neto - ptkpAnnual(ptkpKode)) / 1000) * 1000);
  return Math.round(hitungPPh21Tahunan(pkp) / 12);
}
function generatePayroll(bulan){
  const u = currentUser();
  if(!u || u.role !== 'HRD') throw new Error('Hanya HRD yang dapat membuat payroll.');
  const settings = DB.officeSettings();
  const attendance = DB.attendance().filter(a => a.tanggal.startsWith(bulan));
  const overtime = DB.overtimeRequests().filter(r => r.status === 'DISETUJUI' && r.tanggal.startsWith(bulan));
  const employees = DB.employees().filter(e => e.status === 'AKTIF');

  const results = employees.map(emp => {
    const gajiPokok = Number(emp.gajiPokok) || 0;
    const tunjanganTetap = Number(emp.tunjanganTetap) || 0;
    const tarifLembur = Number(emp.tarifLemburPerJam) || 0;
    const jamLembur = overtime.filter(r => r.employeeId === emp.id).reduce((s,r) => s + (r.totalJam||0), 0);
    const uangLembur = Math.round(jamLembur * tarifLembur);
    const hariTelat = attendance.filter(a => a.employeeId === emp.id && a.statusPulang === 'PULANG_CEPAT_PERLU_IZIN').length;
    const potonganTelat = hariTelat * (Number(settings.potonganTelatPerHari) || 0);

    const bruto = gajiPokok + tunjanganTetap + uangLembur;

    // BPJS: tiap karyawan bisa override persentase sendiri sesuai kontrak, kalau kosong pakai default Pengaturan Kantor
    const pct = (override, fallback) => override != null ? Number(override) : Number(fallback)||0;
    const ikutTk = emp.ikutBpjsTK !== false; // default ikut
    const ikutKes = !!emp.ikutBpjsKesehatan; // default tidak ikut
    const bpjsTkKaryawan = ikutTk ? Math.round(bruto * pct(emp.bpjsTkKaryawanPersen, settings.bpjsTkKaryawanPersen) / 100) : 0;
    const bpjsTkPerusahaan = ikutTk ? Math.round(bruto * pct(emp.bpjsTkPerusahaanPersen, settings.bpjsTkPerusahaanPersen) / 100) : 0;
    const bpjsKesKaryawan = ikutKes ? Math.round(bruto * pct(emp.bpjsKesehatanKaryawanPersen, settings.bpjsKesehatanKaryawanPersen) / 100) : 0;
    const bpjsKesPerusahaan = ikutKes ? Math.round(bruto * pct(emp.bpjsKesehatanPerusahaanPersen, settings.bpjsKesehatanPerusahaanPersen) / 100) : 0;
    const totalBpjsKaryawan = bpjsTkKaryawan + bpjsKesKaryawan;

    // PPh 21: dihitung dulu total pajaknya, lalu dibagi antara karyawan & perusahaan sesuai skema kontrak
    const pph21Total = hitungPPh21Bulanan(bruto, emp.statusPTKP, totalBpjsKaryawan);
    const persenPerusahaan = Math.min(100, Math.max(0, Number(emp.pph21DitanggungPerusahaanPersen)||0));
    const pph21Perusahaan = Math.round(pph21Total * persenPerusahaan / 100);
    const pph21Karyawan = pph21Total - pph21Perusahaan;

    const totalPotongan = potonganTelat + totalBpjsKaryawan + pph21Karyawan;
    const gajiBersih = bruto - totalPotongan;

    return {
      id: uid('PAY'), periode: bulan, employeeId: emp.id, nama: emp.nama, jabatan: emp.jabatan, departemen: emp.departemen,
      gajiPokok, tunjanganTetap, jamLembur, uangLembur, hariTelat, potonganTelat,
      ikutBpjsTK: ikutTk, ikutBpjsKesehatan: ikutKes,
      bpjsTkKaryawan, bpjsTkPerusahaan, bpjsKesKaryawan, bpjsKesPerusahaan,
      ptkp: emp.statusPTKP||'TK0', pph21Total, pph21Karyawan, pph21Perusahaan,
      bruto, totalPotongan, gajiBersih, generatedAt: Date.now(), generatedBy: u.email
    };
  });

  const existing = DB.payrollRuns().filter(p => p.periode !== bulan);
  DB.set('payrollRuns', existing.concat(results));
  writeAudit(u, 'Generate payroll', 'Periode ' + bulan + ' - ' + results.length + ' karyawan', '-', 'SELESAI');
  return results;
}

function getAttendanceToday(emp){
  const employeeId = typeof emp === 'string' ? emp : emp.id;
  const tanggal = typeof emp === 'string' ? todayISO() : shiftAttendanceDate(emp);
  return DB.attendance().find(a => a.employeeId === employeeId && a.tanggal === tanggal);
}

/* Core absen (masuk/pulang) flow shared by both actions.
   type: 'masuk' | 'pulang' */
async function doAbsen(type, onState){
  const u = currentUser();
  if(!u || u.role !== 'KARYAWAN') throw new Error('Hanya karyawan yang dapat melakukan absensi mandiri.');
  const emp = getEmployeeByUserId(u.id);
  if(!emp) throw new Error('Data karyawan tidak ditemukan.');

  const existing = getAttendanceToday(emp);
  if(type === 'masuk' && existing && existing.jamMasuk){
    throw new Error('Anda sudah melakukan absen masuk hari ini.');
  }
  if(type === 'pulang'){
    if(!existing || !existing.jamMasuk) throw new Error('Anda belum absen masuk hari ini.');
    if(existing.jamPulang) throw new Error('Anda sudah melakukan absen pulang hari ini.');
  }

  onState && onState('locating');
  const pos = await getBestPosition();
  const { latitude, longitude, accuracy } = pos.coords;

  if(accuracy > GPS_ACCURACY_LIMIT){
    const err = new Error('Lokasi Anda kurang akurat. Aktifkan lokasi presisi/GPS dan coba lagi.');
    err.code = 'LOW_ACCURACY';
    err.accuracy = accuracy;
    throw err;
  }

  const settings = DB.officeSettings();
  const jarak = haversineDistance(latitude, longitude, settings.lat, settings.lng);

  if(jarak > settings.radius){
    writeAudit(u, 'Absen ' + type + ' DITOLAK (di luar radius)', emp.nama + ' - jarak ' + Math.round(jarak) + 'm', '-', 'DITOLAK');
    const err = new Error('Absen ditolak. Anda berada di luar radius absensi (jarak ' + Math.round(jarak) + ' meter dari kantor, maksimum ' + settings.radius + ' meter).');
    err.code = 'OUT_OF_RADIUS';
    err.jarak = jarak;
    throw err;
  }

  const list = DB.attendance();
  const now = new Date();
  const timeStr = nowTimeStr();
  const userAgent = navigator.userAgent;

  if(type === 'masuk'){
    const jamKerja = jamKerjaFor(emp, settings);
    const tanggalAbsen = shiftAttendanceDate(emp);
    // Kalau tanggal ini sudah kadung ditandai ALPHA oleh deteksi otomatis (belum ada jam masuk asli),
    // timpa record itu di tempat, jangan bikin baris baru (biar tidak dobel).
    const alphaPlaceholder = list.find(a => a.employeeId === emp.id && a.tanggal === tanggalAbsen && a.statusMasuk === 'ALPHA' && !a.jamMasuk);
    const record = alphaPlaceholder || {
      id: uid('ATT'), employeeId: emp.id, nama: emp.nama, tanggal: tanggalAbsen,
      latPulang: null, lngPulang: null, accPulang: null, jarakPulang: null, jamPulang: '', timestampPulang: null
    };
    Object.assign(record, {
      shift: jamKerja.kode || '',
      jamMasuk: timeStr,
      latMasuk: latitude, lngMasuk: longitude, accMasuk: accuracy, jarakMasuk: Math.round(jarak),
      statusMasuk: 'HADIR', userAgent, timestampMasuk: now.getTime()
    });
    if(!alphaPlaceholder) list.push(record);
    DB.set('attendance', list);
    writeAudit(u, 'Absen masuk', emp.nama + ' - ' + timeStr + ' (' + Math.round(jarak) + 'm)', '-', 'HADIR');
    return { record, jarak: Math.round(jarak), status: 'HADIR', accuracy };
  } else {
    existing.jamPulang = timeStr;
    existing.latPulang = latitude; existing.lngPulang = longitude; existing.accPulang = accuracy;
    existing.jarakPulang = Math.round(jarak);
    existing.timestampPulang = now.getTime();
    // Aturan: kalau total jam kerja hari itu kurang dari 5 jam, wajib izin HR - ditandai buat ditindaklanjuti,
    // bukan otomatis ditolak (siapa tau memang sudah izin lisan/tertulis di luar sistem).
    const jamKerjaTotal = existing.timestampMasuk ? (existing.timestampPulang - existing.timestampMasuk) / 3600000 : null;
    existing.jamKerjaTotal = jamKerjaTotal != null ? Math.round(jamKerjaTotal * 10) / 10 : null;
    existing.statusPulang = (jamKerjaTotal != null && jamKerjaTotal < 5) ? 'PULANG_CEPAT_PERLU_IZIN' : 'NORMAL';
    DB.set('attendance', list.map(a => a.id === existing.id ? existing : a));
    writeAudit(u, 'Absen pulang', emp.nama + ' - ' + timeStr + ' (' + Math.round(jarak) + 'm, ' + (existing.jamKerjaTotal||'-') + ' jam kerja)', '-', existing.statusPulang);
    return { record: existing, jarak: Math.round(jarak), status: existing.statusPulang, accuracy };
  }
}

/* ---------------------------------------------------------------------
   8. CUTI / IZIN / LEMBUR
--------------------------------------------------------------------- */
function ajukanCuti(payload){
  const u = currentUser();
  if(!u || u.role !== 'KARYAWAN') throw new Error('Hanya karyawan yang dapat mengajukan cuti.');
  const emp = getEmployeeByUserId(u.id);
  const jumlahHari = daysBetween(payload.tglMulai, payload.tglSelesai) + 1;
  if(jumlahHari < 1) throw new Error('Tanggal selesai tidak boleh sebelum tanggal mulai.');
  const list = DB.leaveRequests();
  const record = {
    id: uid('CUTI'), employeeId: emp.id, nama: emp.nama, jenisCuti: payload.jenisCuti,
    tglMulai: payload.tglMulai, tglSelesai: payload.tglSelesai, jumlahHari,
    alasan: payload.alasan, lampiran: payload.lampiran || '',
    status: 'MENUNGGU_APPROVAL', approvedBy:null, approvedAt:null, rejectedBy:null, rejectedAt:null, rejectionReason:null,
    createdAt: Date.now()
  };
  list.push(record); DB.set('leaveRequests', list);
  writeAudit(u, 'Mengajukan cuti', emp.nama + ' - ' + payload.jenisCuti, '-', 'MENUNGGU_APPROVAL');
  pushNotification(null, 'HRD', emp.nama + ' mengajukan cuti (' + payload.jenisCuti + ').');
  return record;
}
function ajukanIzin(payload){
  const u = currentUser();
  if(!u || u.role !== 'KARYAWAN') throw new Error('Hanya karyawan yang dapat mengajukan izin.');
  const emp = getEmployeeByUserId(u.id);
  const list = DB.permissionRequests();
  const record = {
    id: uid('IZIN'), employeeId: emp.id, nama: emp.nama, tanggal: payload.tanggal, jenisIzin: payload.jenisIzin,
    jamMulai: payload.jamMulai, jamSelesai: payload.jamSelesai, alasan: payload.alasan, lampiran: payload.lampiran || '',
    status: 'MENUNGGU_APPROVAL', approvedBy:null, approvedAt:null, rejectedBy:null, rejectedAt:null, rejectionReason:null,
    createdAt: Date.now()
  };
  list.push(record); DB.set('permissionRequests', list);
  writeAudit(u, 'Mengajukan izin', emp.nama + ' - ' + payload.jenisIzin, '-', 'MENUNGGU_APPROVAL');
  pushNotification(null, 'HRD', emp.nama + ' mengajukan izin (' + payload.jenisIzin + ').');
  return record;
}
function hitungJamLembur(jamMulai, jamSelesai){
  const [h1,m1] = jamMulai.split(':').map(Number);
  const [h2,m2] = jamSelesai.split(':').map(Number);
  let mins = (h2*60+m2) - (h1*60+m1);
  if(mins < 0) mins += 24*60;
  return Math.round((mins/60) * 100) / 100;
}
function ajukanLembur(payload){
  const u = currentUser();
  if(!u || u.role !== 'KARYAWAN') throw new Error('Hanya karyawan yang dapat mengajukan lembur.');
  const emp = getEmployeeByUserId(u.id);
  const totalJam = hitungJamLembur(payload.jamMulai, payload.jamSelesai);
  if(totalJam <= 0) throw new Error('Jam selesai harus setelah jam mulai.');
  const list = DB.overtimeRequests();
  const record = {
    id: uid('LMBR'), employeeId: emp.id, nama: emp.nama, tanggal: payload.tanggal,
    jamMulai: payload.jamMulai, jamSelesai: payload.jamSelesai, totalJam, alasan: payload.alasan,
    status: 'MENUNGGU_APPROVAL', approvedBy:null, approvedAt:null, rejectedBy:null, rejectedAt:null, rejectionReason:null,
    createdAt: Date.now()
  };
  list.push(record); DB.set('overtimeRequests', list);
  writeAudit(u, 'Mengajukan lembur', emp.nama + ' - ' + payload.tanggal + ' (' + totalJam + ' jam)', '-', 'MENUNGGU_APPROVAL');
  pushNotification(null, 'HRD', emp.nama + ' mengajukan lembur pada ' + fmtDate(payload.tanggal) + '.');
  return record;
}

function approveRequest(kind, id){
  const hrd = requireRole('HRD'); // server-side-style guard, not just a hidden button
  const collectionName = kind === 'cuti' ? 'leaveRequests' : kind === 'izin' ? 'permissionRequests' : 'overtimeRequests';
  const list = DB[collectionName]();
  const idx = list.findIndex(r => r.id === id);
  if(idx === -1) throw new Error('Data pengajuan tidak ditemukan.');
  const before = list[idx].status;
  list[idx].status = 'DISETUJUI';
  list[idx].approvedBy = hrd.email;
  list[idx].approvedAt = Date.now();
  DB.set(collectionName, list);
  writeAudit(hrd, 'Menyetujui ' + kind + ' - ' + list[idx].nama, list[idx].id, before, 'DISETUJUI');
  pushNotification(list[idx].employeeId, null, 'Pengajuan ' + kind + ' Anda telah disetujui.');
  return list[idx];
}
function rejectRequest(kind, id, reason){
  const hrd = requireRole('HRD');
  if(!reason || !reason.trim()) throw new Error('Alasan penolakan wajib diisi.');
  const collectionName = kind === 'cuti' ? 'leaveRequests' : kind === 'izin' ? 'permissionRequests' : 'overtimeRequests';
  const list = DB[collectionName]();
  const idx = list.findIndex(r => r.id === id);
  if(idx === -1) throw new Error('Data pengajuan tidak ditemukan.');
  const before = list[idx].status;
  list[idx].status = 'DITOLAK';
  list[idx].rejectedBy = hrd.email;
  list[idx].rejectedAt = Date.now();
  list[idx].rejectionReason = reason;
  DB.set(collectionName, list);
  writeAudit(hrd, 'Menolak ' + kind + ' - ' + list[idx].nama, list[idx].id + ' (' + reason + ')', before, 'DITOLAK');
  pushNotification(list[idx].employeeId, null, 'Pengajuan ' + kind + ' Anda ditolak. Alasan: ' + reason);
  return list[idx];
}

/* ---------------------------------------------------------------------
   9. EMPLOYEE MANAGEMENT (HRD only - guarded server-side-style)
--------------------------------------------------------------------- */
function createEmployee(payload, createLogin){
  const hrd = requireRole('HRD');
  const employees = DB.employees();
  const id = uid('EMP');
  const record = Object.assign({id, status:'AKTIF'}, payload);
  employees.push(record);
  DB.set('employees', employees);
  writeAudit(hrd, 'Menambah karyawan', record.nama, '-', 'AKTIF');
  if(createLogin && payload.email && payload.loginPassword){
    const users = DB.users();
    users.push({id: uid('USR'), email: payload.email, password: payload.loginPassword, role:'KARYAWAN', employeeId:id, active:true});
    DB.set('users', users);
    writeAudit(hrd, 'Membuat akun login karyawan', payload.email, '-', 'KARYAWAN');
  }
  return record;
}
function bulkImportEmployeesFromExcel(){
  const hrd = requireRole('HRD');
  const existing = DB.employees();
  const existingIds = new Set(existing.map(e => e.id));
  const toAdd = EXCEL_IMPORT_EMPLOYEES.filter(e => !existingIds.has(e.id));
  if(!toAdd.length) throw new Error('Data ini sudah pernah di-import sebelumnya.');
  DB.set('employees', existing.concat(toAdd));
  writeAudit(hrd, 'Import karyawan dari Excel', toAdd.length + ' karyawan baru', '-', 'AKTIF');
  return toAdd.length;
}
function updateEmployee(id, payload){
  const hrd = requireRole('HRD');
  const employees = DB.employees();
  const idx = employees.findIndex(e => e.id === id);
  if(idx === -1) throw new Error('Karyawan tidak ditemukan.');
  const before = JSON.stringify(employees[idx]);
  employees[idx] = Object.assign({}, employees[idx], payload);
  DB.set('employees', employees);
  writeAudit(hrd, 'Mengubah data karyawan', employees[idx].nama, 'diubah', 'tersimpan');
  return employees[idx];
}
function setEmployeeStatus(id, status){
  const hrd = requireRole('HRD');
  const employees = DB.employees();
  const idx = employees.findIndex(e => e.id === id);
  if(idx === -1) throw new Error('Karyawan tidak ditemukan.');
  const before = employees[idx].status;
  employees[idx].status = status;
  DB.set('employees', employees);
  const users = DB.users();
  const uIdx = users.findIndex(u => u.employeeId === id);
  if(uIdx !== -1){ users[uIdx].active = (status === 'AKTIF'); DB.set('users', users); }
  writeAudit(hrd, 'Mengubah status karyawan', employees[idx].nama, before, status);
  return employees[idx];
}

/* ---------------------------------------------------------------------
   10. OFFICE SETTINGS / LEAVE TYPES / USERS (HRD only)
--------------------------------------------------------------------- */
function updateOfficeSettings(payload){
  const hrd = requireRole('HRD');
  const before = DB.officeSettings();
  DB.set('officeSettings', Object.assign({}, before, payload));
  writeAudit(hrd, 'Mengubah pengaturan kantor', JSON.stringify(payload), JSON.stringify(before), 'tersimpan');
  return DB.officeSettings();
}
function addLeaveType(nama){
  const hrd = requireRole('HRD');
  const list = DB.leaveTypes();
  const record = {id: uid('LT'), nama};
  list.push(record); DB.set('leaveTypes', list);
  writeAudit(hrd, 'Menambah jenis cuti', nama, '-', 'tersimpan');
  return record;
}
function removeLeaveType(id){
  const hrd = requireRole('HRD');
  const list = DB.leaveTypes().filter(l => l.id !== id);
  DB.set('leaveTypes', list);
  writeAudit(hrd, 'Menghapus jenis cuti', id, '-', 'dihapus');
}
function createHRDUser(email, password, employeeId){
  const hrd = requireRole('HRD');
  if(DB.users().find(u => u.email.toLowerCase() === email.toLowerCase())) throw new Error('Email sudah terdaftar.');
  const users = DB.users();
  users.push({id: uid('USR'), email, password, role:'HRD', employeeId: employeeId || null, active:true});
  DB.set('users', users);
  writeAudit(hrd, 'Menambah akun HRD baru', email, '-', 'HRD');
}
function setUserActive(userId, active){
  const hrd = requireRole('HRD');
  const users = DB.users();
  const idx = users.findIndex(u => u.id === userId);
  if(idx === -1) throw new Error('User tidak ditemukan.');
  users[idx].active = active;
  DB.set('users', users);
  writeAudit(hrd, active ? 'Mengaktifkan akun user' : 'Menonaktifkan akun user', users[idx].email, '-', active ? 'AKTIF' : 'NONAKTIF');
}

/* ---------------------------------------------------------------------
   11. CONTRACT MONITORING
--------------------------------------------------------------------- */
function contractStatus(kontrakSelesai){
  if(!kontrakSelesai) return {label:'TIDAK ADA BATAS (PKWTT)', level:'muted', sisaHari:null};
  const sisa = daysBetween(todayISO(), kontrakSelesai);
  if(sisa < 0) return {label:'KONTRAK BERAKHIR', level:'danger', sisaHari:sisa};
  if(sisa <= 30) return {label:'KONTRAK SEGERA BERAKHIR', level:'danger', sisaHari:sisa};
  if(sisa <= 60) return {label:'KONTRAK AKAN BERAKHIR', level:'warning', sisaHari:sisa};
  return {label:'AKTIF', level:'success', sisaHari:sisa};
}
function contractSummary(){
  const employees = DB.employees().filter(e => e.status === 'AKTIF');
  let aktif=0, w60=0, w30=0, berakhir=0;
  employees.forEach(e => {
    const st = contractStatus(e.kontrakSelesai);
    if(st.sisaHari === null){ aktif++; return; }
    if(st.sisaHari < 0) berakhir++;
    else if(st.sisaHari <= 30) w30++;
    else if(st.sisaHari <= 60) w60++;
    else aktif++;
  });
  return {aktif, w60, w30, berakhir};
}

/* ---------------------------------------------------------------------
   12. CSV EXPORT
--------------------------------------------------------------------- */
function toCSV(rows, headers){
  const escapeCell = v => {
    if(v === null || v === undefined) v = '';
    v = String(v);
    if(/[",\n]/.test(v)) v = '"' + v.replace(/"/g,'""') + '"';
    return v;
  };
  const lines = [headers.map(h => escapeCell(h.label)).join(',')];
  rows.forEach(row => {
    lines.push(headers.map(h => escapeCell(typeof h.value === 'function' ? h.value(row) : row[h.value])).join(','));
  });
  return '\uFEFF' + lines.join('\n');
}
function downloadCSV(filename, csvString){
  const blob = new Blob([csvString], {type:'text/csv;charset=utf-8;'});
  const url = URL.createObjectURL(blob);
  const a = document.createElement('a');
  a.href = url; a.download = filename;
  document.body.appendChild(a); a.click(); document.body.removeChild(a);
  URL.revokeObjectURL(url);
}

/* =====================================================================
   13. UI STATE & ROUTER
   ===================================================================== */
let ROUTE = { page: 'dashboard', params: {} };
let UI = { sidebarOpen:false, gpsState:null, gpsError:null, selectedCalDate:null, calMonth:new Date().getMonth(), calYear:new Date().getFullYear(), alphaChecked:false };
const PAGE_SIZE = 8;

function goTo(page, params){
  ROUTE = { page, params: params || {} };
  UI.sidebarOpen = false;
  render();
  window.scrollTo(0,0);
}

function render(){
  const app = document.getElementById('app');
  const u = currentUser();
  if(!u){
    app.innerHTML = renderLogin();
    bindLoginEvents();
    return;
  }
  app.innerHTML = renderShell(u);
  bindShellEvents(u);
}

/* ---------------------------------------------------------------------
   14. LOGIN PAGE
--------------------------------------------------------------------- */
function renderLogin(){
  return `
  <div class="login-wrap">
    <div class="login-card">
      <div class="login-brand">PT Raja Roti Cemerlang</div>
      <h1 class="login-title">Masuk ke HR Internal</h1>
      <div id="loginError"></div>
      <form id="loginForm">
        <div class="field">
          <label>Email</label>
          <input type="email" id="loginEmail" required placeholder="nama@rajacemerlang.com" autocomplete="username">
        </div>
        <div class="field">
          <label>Kata sandi</label>
          <input type="password" id="loginPassword" required placeholder="Kata sandi" autocomplete="current-password">
        </div>
        <button type="submit" class="btn btn-primary btn-block">Masuk</button>
      </form>
    </div>
  </div>`;
}
function bindLoginEvents(){
  const form = document.getElementById('loginForm');
  form.addEventListener('submit', e => {
    e.preventDefault();
    const email = document.getElementById('loginEmail').value.trim();
    const password = document.getElementById('loginPassword').value;
    const res = login(email, password);
    if(!res.ok){
      document.getElementById('loginError').innerHTML = `<div class="login-error">${escapeHtml(res.message)}</div>`;
      return;
    }
    ROUTE = { page:'dashboard', params:{} };
    render();
  });
}

/* ---------------------------------------------------------------------
   15. SHELL (sidebar + topbar + bottom nav)
--------------------------------------------------------------------- */
function navItemsFor(role){
  if(role === 'HRD'){
    return [
      {group:'Utama', items:[
        {page:'dashboard', label:'Dashboard', icon:'\u{1F4CA}'},
        {page:'kalender', label:'Kalender HR', icon:'\u{1F4C5}'}
      ]},
      {group:'Karyawan', items:[
        {page:'employees', label:'Data Karyawan', icon:'\u{1F465}'},
        {page:'contracts', label:'Monitoring Kontrak', icon:'\u{1F4C4}'}
      ]},
      {group:'Kehadiran', items:[
        {page:'attendance-all', label:'Absensi Semua', icon:'\u{1F4CD}'},
        {page:'overtime-recap', label:'Rekap Lembur', icon:'\u{23F1}'},
        {page:'roster-shift', label:'Roster Shift', icon:'\u{1F4C5}'}
      ]},
      {group:'Payroll', items:[
        {page:'payroll', label:'Payroll', icon:'\u{1F4B0}'}
      ]},
      {group:'Approval', items:[
        {page:'approvals', label:'Approval Pengajuan', icon:'\u{2705}'}
      ]},
      {group:'Sistem', items:[
        {page:'settings', label:'Pengaturan Kantor', icon:'\u{2699}'},
        {page:'audit', label:'Audit Log', icon:'\u{1F4DC}'},
        {page:'profile', label:'Profil Saya', icon:'\u{1F464}'}
      ]}
    ];
  }
  return [
    {group:'Utama', items:[
      {page:'dashboard', label:'Dashboard', icon:'\u{1F4CA}'},
      {page:'attendance', label:'Absensi', icon:'\u{1F4CD}'}
    ]},
    {group:'Pengajuan', items:[
      {page:'cuti', label:'Cuti', icon:'\u{1F3D6}'},
      {page:'izin', label:'Izin', icon:'\u{1F4DD}'},
      {page:'lembur', label:'Lembur', icon:'\u{23F1}'}
    ]},
    {group:'Lainnya', items:[
      {page:'riwayat', label:'Riwayat Absensi', icon:'\u{1F4D6}'},
      {page:'profile', label:'Profil', icon:'\u{1F464}'}
    ]}
  ];
}
function bottomNavFor(role){
  if(role === 'HRD'){
    return [
      {page:'dashboard', label:'Dashboard', icon:'\u{1F4CA}'},
      {page:'employees', label:'Karyawan', icon:'\u{1F465}'},
      {page:'approvals', label:'Approval', icon:'\u{2705}'},
      {page:'contracts', label:'Kontrak', icon:'\u{1F4C4}'},
      {page:'profile', label:'Profil', icon:'\u{1F464}'}
    ];
  }
  return [
    {page:'dashboard', label:'Dashboard', icon:'\u{1F4CA}'},
    {page:'attendance', label:'Absen', icon:'\u{1F4CD}'},
    {page:'cuti', label:'Cuti', icon:'\u{1F3D6}'},
    {page:'riwayat', label:'Riwayat', icon:'\u{1F4D6}'},
    {page:'profile', label:'Profil', icon:'\u{1F464}'}
  ];
}
function pageTitle(page){
  const map = {
    dashboard:'Dashboard', attendance:'Absensi', cuti:'Cuti', izin:'Izin', lembur:'Lembur',
    riwayat:'Riwayat Absensi', profile:'Profil Saya', employees:'Data Karyawan', contracts:'Monitoring Kontrak',
    'attendance-all':'Absensi Semua Karyawan', 'overtime-recap':'Rekap Lembur', approvals:'Approval Pengajuan',
    settings:'Pengaturan Kantor', audit:'Audit Log', kalender:'Kalender HR', payroll:'Payroll', 'roster-shift':'Roster Shift Mingguan'
  };
  return map[page] || 'HR Raja Roti Cemerlang';
}
function renderShell(u){
  const emp = getEmployeeByUserId(u.id);
  const groups = navItemsFor(u.role);
  const bnav = bottomNavFor(u.role);
  const sidebarLinks = groups.map(g => `
    <div class="sidebar-group">${escapeHtml(g.group)}</div>
    ${g.items.map(it => `<a href="#" class="sidebar-link ${ROUTE.page===it.page?'active':''}" data-nav="${it.page}"><span>${it.icon}</span><span>${it.label}</span></a>`).join('')}
  `).join('');

  return `
  <div class="overlay-dim ${UI.sidebarOpen?'show':''}" id="overlayDim"></div>
  <div class="shell">
    <aside class="sidebar ${UI.sidebarOpen?'open':''}" id="sidebar">
      <div class="sidebar-brand">
        <div class="name">Raja Roti Cemerlang</div>
        <div class="sub">HR Internal System</div>
      </div>
      <nav class="sidebar-nav">${sidebarLinks}</nav>
      <div class="sidebar-foot">
        <div class="sidebar-user">${escapeHtml(emp ? emp.nama : u.email)}</div>
        <div class="sidebar-role">${u.role === 'HRD' ? 'HRD' : 'Karyawan'}${emp ? ' &middot; ' + escapeHtml(emp.jabatan) : ''}</div>
        <button class="btn btn-outline btn-block btn-sm" id="logoutBtn">Keluar</button>
      </div>
    </aside>
    <div class="main">
      <div class="topbar">
        <div style="display:flex;align-items:center;gap:10px;">
          <button class="hamburger" id="hamburgerBtn">&#9776;</button>
          <div class="topbar-title">${pageTitle(ROUTE.page)}</div>
        </div>
        <div class="small muted">${fmtDate(todayISO())}</div>
      </div>
      <div class="content" id="pageContent">${renderPage(u, emp)}</div>
    </div>
  </div>
  <nav class="bottom-nav">
    <div class="bottom-nav-inner">
      ${bnav.map(it => `<a href="#" class="${ROUTE.page===it.page?'active':''}" data-nav="${it.page}"><span class="bn-icon">${it.icon}</span>${it.label}</a>`).join('')}
    </div>
  </nav>`;
}
function bindShellEvents(u){
  document.querySelectorAll('[data-nav]').forEach(el => {
    el.addEventListener('click', e => { e.preventDefault(); goTo(el.getAttribute('data-nav')); });
  });
  const hb = document.getElementById('hamburgerBtn');
  if(hb) hb.addEventListener('click', () => { UI.sidebarOpen = !UI.sidebarOpen; render(); });
  const dim = document.getElementById('overlayDim');
  if(dim) dim.addEventListener('click', () => { UI.sidebarOpen = false; render(); });
  const lb = document.getElementById('logoutBtn');
  if(lb) lb.addEventListener('click', () => { logout(); ROUTE = {page:'dashboard', params:{}}; render(); });
  bindPageEvents(u);
}

/* ---------------------------------------------------------------------
   16. PAGE ROUTER
--------------------------------------------------------------------- */
function renderPage(u, emp){
  try{
    if(u.role === 'KARYAWAN'){
      switch(ROUTE.page){
        case 'dashboard': return renderKaryawanDashboard(u, emp);
        case 'attendance': return renderAttendancePage(u, emp);
        case 'cuti': return renderCutiPage(emp);
        case 'izin': return renderIzinPage(emp);
        case 'lembur': return renderLemburPage(emp);
        case 'riwayat': return renderRiwayatPage(emp);
        case 'profile': return renderProfilePage(u, emp);
        default: return renderKaryawanDashboard(u, emp);
      }
    } else {
      switch(ROUTE.page){
        case 'dashboard': return renderHRDDashboard();
        case 'employees': return renderEmployeesPage();
        case 'contracts': return renderContractsPage();
        case 'attendance-all': return renderAttendanceAllPage();
        case 'overtime-recap': return renderOvertimeRecapPage();
        case 'roster-shift': return renderRosterShiftPage();
        case 'payroll': return renderPayrollPage();
        case 'approvals': return renderApprovalsPage();
        case 'settings': return renderSettingsPage();
        case 'audit': return renderAuditPage();
        case 'kalender': return renderCalendarPage();
        case 'profile': return renderProfilePage(u, emp);
        default: return renderHRDDashboard();
      }
    }
  } catch(err){
    return `<div class="card"><b>Terjadi kesalahan:</b> ${escapeHtml(err.message)}</div>`;
  }
}
function bindPageEvents(u){
  if(u.role === 'KARYAWAN'){
    switch(ROUTE.page){
      case 'attendance': return bindAttendanceEvents();
      case 'cuti': return bindCutiEvents();
      case 'izin': return bindIzinEvents();
      case 'lembur': return bindLemburEvents();
      case 'riwayat': return bindRiwayatEvents();
      case 'profile': return;
      case 'dashboard': return bindAttendanceEvents();
      default: return;
    }
  } else {
    switch(ROUTE.page){
      case 'employees': return bindEmployeesEvents();
      case 'contracts': return;
      case 'attendance-all': return bindAttendanceAllEvents();
      case 'overtime-recap': return bindOvertimeRecapEvents();
      case 'approvals': return bindApprovalsEvents();
      case 'settings': return bindSettingsEvents();
      case 'audit': return bindAuditEvents();
      case 'roster-shift': return bindRosterShiftEvents();
      case 'payroll': return bindPayrollEvents();
      case 'kalender': return bindCalendarEvents();
      default: return;
    }
  }
}

/* =====================================================================
   17. KARYAWAN PAGES
   ===================================================================== */
function renderAttendanceHero(emp){
  const att = getAttendanceToday(emp);
  const canMasuk = !att || !att.jamMasuk;
  const canPulang = att && att.jamMasuk && !att.jamPulang;
  const settings = DB.officeSettings();
  const jamKerja = jamKerjaFor(emp, settings);
  const jamLabel = jamKerja.nama ? jamKerja.nama : `Jam kantor ${settings.jamMasuk} - ${settings.jamPulang}`;

  let stateBlock = '';
  if(UI.gpsState === 'locating'){
    stateBlock = `<div class="gps-info">Mengambil lokasi GPS, mohon tunggu...</div>`;
  } else if(UI.gpsError){
    if(UI.gpsError.code === 'LOW_ACCURACY'){
      stateBlock = `
        <div class="gps-info">Akurasi GPS: &plusmn;${Math.round(UI.gpsError.accuracy)} meter &mdash; ${escapeHtml(UI.gpsError.message)}</div>
        <button class="btn btn-outline btn-sm" style="margin-top:8px;" id="retryGpsBtn">Coba Lagi</button>`;
    } else {
      stateBlock = `<div class="gps-info" style="color:#F3B3AC;">${escapeHtml(UI.gpsError.message)}</div>
        <button class="btn btn-outline btn-sm" style="margin-top:8px;" id="retryGpsBtn">Coba Lagi</button>`;
    }
  }

  return `
  <div class="attendance-hero">
    <div class="greet">Selamat datang, ${escapeHtml(emp.nama)}</div>
    <div class="date">${fmtDate(todayISO())} &middot; ${jamLabel}</div>
    <div class="attendance-times">
      <div><div class="t-label">Jam Masuk</div><div class="t-val">${att && att.jamMasuk ? att.jamMasuk : '--:--'}</div></div>
      <div><div class="t-label">Jam Pulang</div><div class="t-val">${att && att.jamPulang ? att.jamPulang : '--:--'}</div></div>
      <div><div class="t-label">Status</div><div class="t-val" style="font-size:1rem;">${att ? statusBadge(att.statusMasuk) : '-'}</div></div>
    </div>
    <div class="attendance-actions">
      <button class="btn btn-success" id="absenMasukBtn" ${!canMasuk || UI.gpsState==='locating' ? 'disabled' : ''}>Absen Masuk</button>
      <button class="btn btn-navy" id="absenPulangBtn" ${!canPulang || UI.gpsState==='locating' ? 'disabled' : ''}>Absen Pulang</button>
    </div>
    ${stateBlock}
  </div>`;
}
function statusBadge(status){
  if(status === 'HADIR' || status === 'NORMAL') return `<span class="badge badge-success">Hadir</span>`;
  if(status === 'PULANG_CEPAT_PERLU_IZIN') return `<span class="badge badge-warning">Pulang Cepat - Perlu Izin HR</span>`;
  if(status === 'ALPHA') return `<span class="badge badge-danger">Alpha</span>`;
  if(status === 'MENUNGGU_APPROVAL') return `<span class="badge badge-muted">Menunggu Approval</span>`;
  if(status === 'DISETUJUI') return `<span class="badge badge-success">Disetujui</span>`;
  if(status === 'DITOLAK') return `<span class="badge badge-danger">Ditolak</span>`;
  return `<span class="badge badge-muted">${escapeHtml(status)}</span>`;
}
function renderKaryawanDashboard(u, emp){
  const myLeave = DB.leaveRequests().filter(r => r.employeeId === emp.id).sort((a,b)=>b.createdAt-a.createdAt).slice(0,3);
  const myPerm = DB.permissionRequests().filter(r => r.employeeId === emp.id).sort((a,b)=>b.createdAt-a.createdAt).slice(0,3);
  const myOt = DB.overtimeRequests().filter(r => r.employeeId === emp.id).sort((a,b)=>b.createdAt-a.createdAt).slice(0,3);

  const rowsHtml = (list, cols) => list.length ? list.map(r => `<tr>${cols(r)}</tr>`).join('') : `<tr><td colspan="3" class="empty-row">Belum ada pengajuan</td></tr>`;

  return `
  ${renderAttendanceHero(emp)}
  <div class="section-title">Pengajuan Saya</div>
  <div class="grid grid-3">
    <div class="panel">
      <div class="panel-head"><h3>Cuti</h3><button class="btn btn-outline btn-sm" data-nav="cuti">Ajukan</button></div>
      <div class="table-wrap"><table class="datatable"><tbody>
        ${rowsHtml(myLeave, r => `<td>${fmtDate(r.tglMulai)}</td><td>${escapeHtml(r.jenisCuti)}</td><td>${statusBadge(r.status)}</td>`)}
      </tbody></table></div>
    </div>
    <div class="panel">
      <div class="panel-head"><h3>Izin</h3><button class="btn btn-outline btn-sm" data-nav="izin">Ajukan</button></div>
      <div class="table-wrap"><table class="datatable"><tbody>
        ${rowsHtml(myPerm, r => `<td>${fmtDate(r.tanggal)}</td><td>${escapeHtml(r.jenisIzin)}</td><td>${statusBadge(r.status)}</td>`)}
      </tbody></table></div>
    </div>
    <div class="panel">
      <div class="panel-head"><h3>Lembur</h3><button class="btn btn-outline btn-sm" data-nav="lembur">Ajukan</button></div>
      <div class="table-wrap"><table class="datatable"><tbody>
        ${rowsHtml(myOt, r => `<td>${fmtDate(r.tanggal)}</td><td>${r.totalJam} jam</td><td>${statusBadge(r.status)}</td>`)}
      </tbody></table></div>
    </div>
  </div>`;
}
function renderAttendancePage(u, emp){
  return renderAttendanceHero(emp) + `
  <div class="card small muted" style="margin-top:16px;">
    Sistem akan meminta izin akses lokasi saat Anda menekan tombol absen. Pastikan GPS/lokasi presisi tinggi
    aktif di perangkat Anda agar validasi radius kantor berjalan akurat. Radius absensi saat ini
    <b>${DB.officeSettings().radius} meter</b> dari titik kantor.
  </div>`;
}
function bindAttendanceEvents(){
  const btnMasuk = document.getElementById('absenMasukBtn');
  const btnPulang = document.getElementById('absenPulangBtn');
  const retryBtn = document.getElementById('retryGpsBtn');
  async function run(type){
    UI.gpsError = null; UI.gpsState = 'locating';
    const content = document.getElementById('pageContent');
    if(content) content.innerHTML = ROUTE.page === 'dashboard' ? renderKaryawanDashboard(currentUser(), getEmployeeForCurrentUser()) : renderAttendancePage(currentUser(), getEmployeeForCurrentUser());
    bindAttendanceEvents();
    try{
      const result = await doAbsen(type);
      UI.gpsState = null;
      if(type === 'masuk'){
        toast(`Absen masuk berhasil. Jarak dari kantor: ${result.jarak} meter.`, 'success');
      }else if(result.status === 'PULANG_CEPAT_PERLU_IZIN'){
        toast(`Absen pulang berhasil (${result.jarak} meter). Jam kerja hari ini kurang dari 5 jam - pastikan sudah izin ke HR.`, 'error');
      }else{
        toast(`Absen pulang berhasil. Jarak dari kantor: ${result.jarak} meter.`, 'success');
      }
      render();
    }catch(err){
      UI.gpsState = null;
      UI.gpsError = err;
      if(err.code === 'OUT_OF_RADIUS' || err.code === 'LOW_ACCURACY'){
        toast(err.message, 'error');
      } else if(err.code === undefined && err.message && err.PERMISSION_DENIED !== undefined){
        toast('Izin lokasi ditolak. Aktifkan izin lokasi di browser untuk absen.', 'error');
      } else {
        toast(err.message || 'Gagal mengambil lokasi. Coba lagi.', 'error');
      }
      render();
    }
  }
  if(btnMasuk) btnMasuk.addEventListener('click', () => run('masuk'));
  if(btnPulang) btnPulang.addEventListener('click', () => run('pulang'));
  if(retryBtn) retryBtn.addEventListener('click', () => {
    const att = getAttendanceToday(getEmployeeForCurrentUser());
    run(att && att.jamMasuk ? 'pulang' : 'masuk');
  });
}

function leaveTypeOptions(){
  return DB.leaveTypes().map(lt => `<option value="${escapeHtml(lt.nama)}">${escapeHtml(lt.nama)}</option>`).join('');
}
function renderCutiPage(emp){
  const myLeave = DB.leaveRequests().filter(r => r.employeeId === emp.id).sort((a,b)=>b.createdAt-a.createdAt);
  return `
  <div class="panel" style="margin-bottom:20px;">
    <div class="panel-head"><h3>Ajukan Cuti</h3></div>
    <div class="panel-body">
      <form id="cutiForm">
        <div class="form-row-2">
          <div class="field"><label>Jenis Cuti</label><select id="cJenis" required>${leaveTypeOptions()}</select></div>
          <div class="field"><label>Lampiran (opsional, nama file)</label><input type="text" id="cLampiran" placeholder="mis. surat_dokter.pdf"></div>
        </div>
        <div class="form-row-2">
          <div class="field"><label>Tanggal Mulai</label><input type="date" id="cMulai" required></div>
          <div class="field"><label>Tanggal Selesai</label><input type="date" id="cSelesai" required></div>
        </div>
        <div class="field"><label>Alasan</label><textarea id="cAlasan" rows="3" required></textarea></div>
        <button class="btn btn-primary" type="submit">Ajukan Cuti</button>
      </form>
    </div>
  </div>
  <div class="panel">
    <div class="panel-head"><h3>Riwayat Pengajuan Cuti Saya</h3></div>
    <div class="table-wrap"><table class="datatable">
      <thead><tr><th>Jenis</th><th>Mulai</th><th>Selesai</th><th>Hari</th><th>Status</th><th>Catatan</th></tr></thead>
      <tbody>${myLeave.length ? myLeave.map(r => `<tr>
        <td>${escapeHtml(r.jenisCuti)}</td><td>${fmtDate(r.tglMulai)}</td><td>${fmtDate(r.tglSelesai)}</td><td>${r.jumlahHari}</td>
        <td>${statusBadge(r.status)}</td><td class="small muted">${r.status==='DITOLAK' ? escapeHtml(r.rejectionReason||'') : ''}</td>
      </tr>`).join('') : `<tr><td colspan="6" class="empty-row">Belum ada pengajuan cuti</td></tr>`}</tbody>
    </table></div>
  </div>`;
}
function bindCutiEvents(){
  const form = document.getElementById('cutiForm');
  if(!form) return;
  form.addEventListener('submit', e => {
    e.preventDefault();
    try{
      ajukanCuti({
        jenisCuti: document.getElementById('cJenis').value,
        tglMulai: document.getElementById('cMulai').value,
        tglSelesai: document.getElementById('cSelesai').value,
        alasan: document.getElementById('cAlasan').value,
        lampiran: document.getElementById('cLampiran').value
      });
      toast('Pengajuan berhasil dikirim dan menunggu approval HRD.', 'success');
      render();
    }catch(err){ toast(err.message, 'error'); }
  });
}

function renderIzinPage(emp){
  const myPerm = DB.permissionRequests().filter(r => r.employeeId === emp.id).sort((a,b)=>b.createdAt-a.createdAt);
  return `
  <div class="panel" style="margin-bottom:20px;">
    <div class="panel-head"><h3>Ajukan Izin</h3></div>
    <div class="panel-body">
      <form id="izinForm">
        <div class="form-row-2">
          <div class="field"><label>Tanggal</label><input type="date" id="iTanggal" required></div>
          <div class="field"><label>Jenis Izin</label><input type="text" id="iJenis" placeholder="mis. Keperluan keluarga" required></div>
        </div>
        <div class="form-row-2">
          <div class="field"><label>Jam Mulai</label><input type="time" id="iMulai" required></div>
          <div class="field"><label>Jam Selesai</label><input type="time" id="iSelesai" required></div>
        </div>
        <div class="field"><label>Alasan</label><textarea id="iAlasan" rows="3" required></textarea></div>
        <button class="btn btn-primary" type="submit">Ajukan Izin</button>
      </form>
    </div>
  </div>
  <div class="panel">
    <div class="panel-head"><h3>Riwayat Pengajuan Izin Saya</h3></div>
    <div class="table-wrap"><table class="datatable">
      <thead><tr><th>Tanggal</th><th>Jenis</th><th>Jam</th><th>Status</th><th>Catatan</th></tr></thead>
      <tbody>${myPerm.length ? myPerm.map(r => `<tr>
        <td>${fmtDate(r.tanggal)}</td><td>${escapeHtml(r.jenisIzin)}</td><td>${r.jamMulai}-${r.jamSelesai}</td>
        <td>${statusBadge(r.status)}</td><td class="small muted">${r.status==='DITOLAK' ? escapeHtml(r.rejectionReason||'') : ''}</td>
      </tr>`).join('') : `<tr><td colspan="5" class="empty-row">Belum ada pengajuan izin</td></tr>`}</tbody>
    </table></div>
  </div>`;
}
function bindIzinEvents(){
  const form = document.getElementById('izinForm');
  if(!form) return;
  form.addEventListener('submit', e => {
    e.preventDefault();
    try{
      ajukanIzin({
        tanggal: document.getElementById('iTanggal').value,
        jenisIzin: document.getElementById('iJenis').value,
        jamMulai: document.getElementById('iMulai').value,
        jamSelesai: document.getElementById('iSelesai').value,
        alasan: document.getElementById('iAlasan').value
      });
      toast('Pengajuan berhasil dikirim dan menunggu approval HRD.', 'success');
      render();
    }catch(err){ toast(err.message, 'error'); }
  });
}

function renderLemburPage(emp){
  const myOt = DB.overtimeRequests().filter(r => r.employeeId === emp.id).sort((a,b)=>b.createdAt-a.createdAt);
  return `
  <div class="panel" style="margin-bottom:20px;">
    <div class="panel-head"><h3>Ajukan Lembur</h3></div>
    <div class="panel-body">
      <form id="lemburForm">
        <div class="field"><label>Tanggal</label><input type="date" id="lTanggal" required></div>
        <div class="form-row-2">
          <div class="field"><label>Jam Mulai</label><input type="time" id="lMulai" required></div>
          <div class="field"><label>Jam Selesai</label><input type="time" id="lSelesai" required></div>
        </div>
        <div class="field"><label>Alasan</label><textarea id="lAlasan" rows="3" required></textarea></div>
        <button class="btn btn-primary" type="submit">Ajukan Lembur</button>
      </form>
    </div>
  </div>
  <div class="panel">
    <div class="panel-head"><h3>Riwayat Pengajuan Lembur Saya</h3></div>
    <div class="table-wrap"><table class="datatable">
      <thead><tr><th>Tanggal</th><th>Jam</th><th>Total Jam</th><th>Status</th><th>Catatan</th></tr></thead>
      <tbody>${myOt.length ? myOt.map(r => `<tr>
        <td>${fmtDate(r.tanggal)}</td><td>${r.jamMulai}-${r.jamSelesai}</td><td>${r.totalJam}</td>
        <td>${statusBadge(r.status)}</td><td class="small muted">${r.status==='DITOLAK' ? escapeHtml(r.rejectionReason||'') : ''}</td>
      </tr>`).join('') : `<tr><td colspan="5" class="empty-row">Belum ada pengajuan lembur</td></tr>`}</tbody>
    </table></div>
  </div>`;
}
function bindLemburEvents(){
  const form = document.getElementById('lemburForm');
  if(!form) return;
  form.addEventListener('submit', e => {
    e.preventDefault();
    try{
      ajukanLembur({
        tanggal: document.getElementById('lTanggal').value,
        jamMulai: document.getElementById('lMulai').value,
        jamSelesai: document.getElementById('lSelesai').value,
        alasan: document.getElementById('lAlasan').value
      });
      toast('Pengajuan berhasil dikirim dan menunggu approval HRD.', 'success');
      render();
    }catch(err){ toast(err.message, 'error'); }
  });
}

function renderRiwayatPage(emp){
  const all = DB.attendance().filter(a => a.employeeId === emp.id).sort((a,b)=>b.tanggal.localeCompare(a.tanggal));
  const params = ROUTE.params || {};
  const bulan = params.bulan || '';
  const filtered = bulan ? all.filter(a => a.tanggal.startsWith(bulan)) : all;
  return `
  <div class="panel">
    <div class="panel-head">
      <h3>Riwayat Absensi Saya</h3>
      <div class="toolbar">
        <input type="month" id="riwayatBulan" value="${escapeHtml(bulan)}">
      </div>
    </div>
    <div class="table-wrap"><table class="datatable">
      <thead><tr><th>Tanggal</th><th>Masuk</th><th>Pulang</th><th>Status</th><th>Jarak Masuk</th><th>Jarak Pulang</th></tr></thead>
      <tbody>${filtered.length ? filtered.map(a => `<tr>
        <td>${fmtDate(a.tanggal)}</td><td>${a.jamMasuk||'-'}</td><td>${a.jamPulang||'-'}</td>
        <td>${statusBadge(a.statusMasuk)}${a.statusPulang==='PULANG_CEPAT_PERLU_IZIN' ? ' '+statusBadge(a.statusPulang) : ''}</td><td>${a.jarakMasuk!=null?a.jarakMasuk+' m':'-'}</td><td>${a.jarakPulang!=null?a.jarakPulang+' m':'-'}</td>
      </tr>`).join('') : `<tr><td colspan="6" class="empty-row">Tidak ada data absensi</td></tr>`}</tbody>
    </table></div>
  </div>`;
}
function bindRiwayatEvents(){
  const sel = document.getElementById('riwayatBulan');
  if(sel) sel.addEventListener('change', () => goTo('riwayat', {bulan: sel.value}));
}

function renderProfilePage(u, emp){
  if(!emp) return `<div class="card">Data profil tidak ditemukan.</div>`;
  const isHRD = u.role === 'HRD';
  return `
  <div class="panel">
    <div class="panel-head"><h3>Profil Saya</h3></div>
    <div class="panel-body">
      <div class="kv">
        <div>Nama Lengkap</div><div>${escapeHtml(emp.nama)}</div>
        <div>Email</div><div>${escapeHtml(emp.email)}</div>
        <div>No. HP</div><div>${escapeHtml(emp.hp)}</div>
        <div>Alamat</div><div>${escapeHtml(emp.alamat)}</div>
        <div>Jabatan</div><div>${escapeHtml(emp.jabatan)}</div>
        <div>Departemen</div><div>${escapeHtml(emp.departemen)}</div>
        <div>Atasan</div><div>${escapeHtml(emp.atasan||'-')}</div>
        <div>Jadwal Kerja</div><div>${(findJadwal(getJadwalKerjaKode(emp))||{}).nama || getJadwalKerjaKode(emp)}</div>
        <div>Tanggal Masuk</div><div>${fmtDate(emp.joinDate)}</div>
        <div>Status</div><div>${emp.status==='AKTIF' ? '<span class="badge badge-success">Aktif</span>' : '<span class="badge badge-danger">Nonaktif</span>'}</div>
        ${isHRD ? `
        <div>NIK</div><div>${escapeHtml(emp.nik)}</div>
        <div>No. KK</div><div>${escapeHtml(emp.kk)}</div>
        <div>Jenis Kontrak</div><div>${escapeHtml(emp.jenisKontrak)}</div>
        <div>Berakhir Kontrak</div><div>${emp.kontrakSelesai ? fmtDate(emp.kontrakSelesai) : 'Tidak ada (PKWTT)'}</div>` : ''}
      </div>
      <div class="hint">${isHRD ? '' : 'NIK dan Nomor KK bersifat rahasia dan hanya dapat dilihat oleh HRD.'}</div>
    </div>
  </div>`;
}

/* =====================================================================
   18. HRD PAGES
   ===================================================================== */
function renderHRDDashboard(){
  const employees = DB.employees();
  const activeEmployees = employees.filter(e => e.status === 'AKTIF');
  const todayAtt = DB.attendance().filter(a => a.tanggal === todayISO());
  const hadir = todayAtt.filter(a => a.jamMasuk).length;
  const terlambat = todayAtt.filter(a => a.statusPulang === 'PULANG_CEPAT_PERLU_IZIN').length;
  const belumAbsen = activeEmployees.length - hadir;
  const cutiMenunggu = DB.leaveRequests().filter(r => r.status === 'MENUNGGU_APPROVAL').length;
  const izinMenunggu = DB.permissionRequests().filter(r => r.status === 'MENUNGGU_APPROVAL').length;
  const lemburMenunggu = DB.overtimeRequests().filter(r => r.status === 'MENUNGGU_APPROVAL').length;
  const kontrak = contractSummary();
  const alphaBulanIni = DB.attendance().filter(a => a.statusMasuk === 'ALPHA' && a.tanggal.startsWith(todayISO().slice(0,7))).length;

  const pendingList = getAllPendingApprovals().slice(0,5);

  return `
  <div class="grid grid-4">
    <div class="card stat stat-navy"><div class="num">${activeEmployees.length}</div><div class="label">Total Karyawan Aktif</div></div>
    <div class="card stat stat-success"><div class="num">${hadir}</div><div class="label">Hadir Hari Ini</div></div>
    <div class="card stat stat-warning"><div class="num">${terlambat}</div><div class="label">Pulang Cepat Hari Ini</div></div>
    <div class="card stat stat-danger"><div class="num">${belumAbsen}</div><div class="label">Belum Absen</div></div>
  </div>
  <div class="grid grid-4" style="margin-top:16px;">
    <div class="card stat"><div class="num">${cutiMenunggu}</div><div class="label">Cuti Menunggu Approval</div></div>
    <div class="card stat"><div class="num">${izinMenunggu}</div><div class="label">Izin Menunggu Approval</div></div>
    <div class="card stat"><div class="num">${lemburMenunggu}</div><div class="label">Lembur Menunggu Approval</div></div>
    <div class="card stat stat-danger"><div class="num">${alphaBulanIni}</div><div class="label">Total Alpha Bulan Ini</div></div>
  </div>

  <div class="section-title">Monitoring Kontrak</div>
  <div class="grid grid-4">
    <div class="card stat stat-success"><div class="num">${kontrak.aktif}</div><div class="label">Kontrak Aktif</div></div>
    <div class="card stat stat-warning"><div class="num">${kontrak.w60}</div><div class="label">Berakhir &le; 60 Hari</div></div>
    <div class="card stat stat-danger"><div class="num">${kontrak.w30}</div><div class="label">Berakhir &le; 30 Hari</div></div>
    <div class="card stat stat-danger"><div class="num">${kontrak.berakhir}</div><div class="label">Sudah Berakhir</div></div>
  </div>

  <div class="section-title">Approval Menunggu (terbaru)</div>
  <div class="panel">
    <div class="table-wrap"><table class="datatable">
      <thead><tr><th>Jenis</th><th>Nama</th><th>Tanggal</th><th>Keterangan</th><th>Aksi</th></tr></thead>
      <tbody>${pendingList.length ? pendingList.map(p => `<tr>
        <td>${p.kindLabel}</td><td>${escapeHtml(p.nama)}</td><td>${fmtDate(p.tanggal)}</td><td class="small">${escapeHtml(p.keterangan)}</td>
        <td>
          <button class="btn btn-success btn-sm" data-approve="${p.kind}:${p.id}">Approve</button>
          <button class="btn btn-danger btn-sm" data-reject="${p.kind}:${p.id}">Reject</button>
        </td>
      </tr>`).join('') : `<tr><td colspan="5" class="empty-row">Tidak ada approval yang menunggu</td></tr>`}</tbody>
    </table></div>
  </div>`;
}
function getAllPendingApprovals(){
  const cuti = DB.leaveRequests().filter(r => r.status === 'MENUNGGU_APPROVAL')
    .map(r => ({kind:'cuti', kindLabel:'Cuti', id:r.id, nama:r.nama, tanggal:r.tglMulai, keterangan:r.jenisCuti+' - '+r.alasan, createdAt:r.createdAt}));
  const izin = DB.permissionRequests().filter(r => r.status === 'MENUNGGU_APPROVAL')
    .map(r => ({kind:'izin', kindLabel:'Izin', id:r.id, nama:r.nama, tanggal:r.tanggal, keterangan:r.jenisIzin+' - '+r.alasan, createdAt:r.createdAt}));
  const lembur = DB.overtimeRequests().filter(r => r.status === 'MENUNGGU_APPROVAL')
    .map(r => ({kind:'lembur', kindLabel:'Lembur', id:r.id, nama:r.nama, tanggal:r.tanggal, keterangan:r.totalJam+' jam - '+r.alasan, createdAt:r.createdAt}));
  return [...cuti, ...izin, ...lembur].sort((a,b)=>b.createdAt-a.createdAt);
}
function bindApprovalActionEvents(afterRerender){
  document.querySelectorAll('[data-approve]').forEach(btn => {
    btn.addEventListener('click', () => {
      const [kind, id] = btn.getAttribute('data-approve').split(':');
      try{ approveRequest(kind, id); toast('Pengajuan telah disetujui.', 'success'); afterRerender ? afterRerender() : render(); }
      catch(err){ toast(err.message, 'error'); }
    });
  });
  document.querySelectorAll('[data-reject]').forEach(btn => {
    btn.addEventListener('click', () => {
      const [kind, id] = btn.getAttribute('data-reject').split(':');
      openRejectModal(kind, id, afterRerender);
    });
  });
}
function openRejectModal(kind, id, afterRerender){
  const bg = document.createElement('div');
  bg.className = 'modal-bg';
  bg.innerHTML = `
    <div class="modal">
      <button class="modal-close" id="modalCloseBtn">&times;</button>
      <h3>Tolak Pengajuan</h3>
      <div class="field"><label>Alasan Penolakan</label><textarea id="rejectReason" rows="3" placeholder="Jelaskan alasan penolakan"></textarea></div>
      <button class="btn btn-danger btn-block" id="confirmRejectBtn">Tolak Pengajuan</button>
    </div>`;
  document.body.appendChild(bg);
  document.getElementById('modalCloseBtn').addEventListener('click', () => bg.remove());
  bg.addEventListener('click', e => { if(e.target === bg) bg.remove(); });
  document.getElementById('confirmRejectBtn').addEventListener('click', () => {
    try{
      rejectRequest(kind, id, document.getElementById('rejectReason').value);
      bg.remove();
      toast('Pengajuan telah ditolak.', 'success');
      afterRerender ? afterRerender() : render();
    }catch(err){ toast(err.message, 'error'); }
  });
}

/* ---- Approvals page (full list, filterable by kind) ---- */
function renderApprovalsPage(){
  const filter = (ROUTE.params && ROUTE.params.kind) || 'semua';
  let all = getAllPendingApprovals();
  if(filter !== 'semua') all = all.filter(a => a.kind === filter);
  return `
  <div class="pill-nav">
    ${['semua','cuti','izin','lembur'].map(k => `<button data-filterkind="${k}" class="${filter===k?'active':''}">${k[0].toUpperCase()+k.slice(1)}</button>`).join('')}
  </div>
  <div class="panel">
    <div class="table-wrap"><table class="datatable">
      <thead><tr><th>Jenis</th><th>Nama</th><th>Tanggal</th><th>Keterangan</th><th>Aksi</th></tr></thead>
      <tbody>${all.length ? all.map(p => `<tr>
        <td>${p.kindLabel}</td><td>${escapeHtml(p.nama)}</td><td>${fmtDate(p.tanggal)}</td><td class="small">${escapeHtml(p.keterangan)}</td>
        <td>
          <button class="btn btn-success btn-sm" data-approve="${p.kind}:${p.id}">Approve</button>
          <button class="btn btn-danger btn-sm" data-reject="${p.kind}:${p.id}">Reject</button>
        </td>
      </tr>`).join('') : `<tr><td colspan="5" class="empty-row">Tidak ada pengajuan menunggu approval</td></tr>`}</tbody>
    </table></div>
  </div>`;
}
function bindApprovalsEvents(){
  document.querySelectorAll('[data-filterkind]').forEach(btn => {
    btn.addEventListener('click', () => goTo('approvals', {kind: btn.getAttribute('data-filterkind')}));
  });
  bindApprovalActionEvents(() => goTo('approvals', ROUTE.params));
}

/* ---- Employees page ---- */
function renderEmployeesPage(){
  const p = ROUTE.params || {};
  const search = (p.q || '').toLowerCase();
  const dept = p.dept || '';
  const status = p.status || '';
  const page = p.page || 1;

  let list = DB.employees();
  if(search) list = list.filter(e => e.nama.toLowerCase().includes(search) || e.email.toLowerCase().includes(search) || e.id.toLowerCase().includes(search));
  if(dept) list = list.filter(e => e.departemen === dept);
  if(status) list = list.filter(e => e.status === status);

  const total = list.length;
  const totalPages = Math.max(1, Math.ceil(total / PAGE_SIZE));
  const pageClamped = Math.min(Math.max(1, page), totalPages);
  const pageItems = list.slice((pageClamped-1)*PAGE_SIZE, pageClamped*PAGE_SIZE);

  const depts = [...new Set(DB.employees().map(e => e.departemen))];

  return `
  <div class="panel">
    <div class="panel-head">
      <h3>Data Karyawan (${total})</h3>
      <div class="toolbar">
        <input type="text" id="empSearch" placeholder="Cari nama/email/ID" value="${escapeHtml(p.q||'')}">
        <select id="empDeptFilter"><option value="">Semua Departemen</option>${depts.map(d=>`<option value="${escapeHtml(d)}" ${dept===d?'selected':''}>${escapeHtml(d)}</option>`).join('')}</select>
        <select id="empStatusFilter"><option value="">Semua Status</option><option value="AKTIF" ${status==='AKTIF'?'selected':''}>Aktif</option><option value="NONAKTIF" ${status==='NONAKTIF'?'selected':''}>Nonaktif</option></select>
        <button class="btn btn-outline btn-sm" id="empExportBtn">Export CSV</button>
        <button class="btn btn-outline btn-sm" id="empImportExcelBtn">Import 103 Karyawan dari Excel</button>
        <button class="btn btn-primary btn-sm" id="empAddBtn">+ Tambah Karyawan</button>
      </div>
    </div>
    <div class="table-wrap"><table class="datatable">
      <thead><tr><th>Nama</th><th>NIK</th><th>No. KK</th><th>Jabatan</th><th>Departemen</th><th>Kontrak</th><th>Status</th><th>Aksi</th></tr></thead>
      <tbody>${pageItems.length ? pageItems.map(e => `<tr>
        <td>${escapeHtml(e.nama)}<div class="small muted">${escapeHtml(e.email)}</div></td>
        <td class="small">${escapeHtml(e.nik)}</td>
        <td class="small">${escapeHtml(e.kk)}</td>
        <td>${escapeHtml(e.jabatan)}</td><td>${escapeHtml(e.departemen)}</td>
        <td>${escapeHtml(e.jenisKontrak)}</td>
        <td>${e.status==='AKTIF' ? '<span class="badge badge-success">Aktif</span>' : '<span class="badge badge-danger">Nonaktif</span>'}</td>
        <td>
          <button class="btn btn-outline btn-sm" data-view-emp="${e.id}">Lihat</button>
          <button class="btn btn-outline btn-sm" data-edit-emp="${e.id}">Edit</button>
          ${e.status==='AKTIF'
            ? `<button class="btn btn-danger btn-sm" data-deactivate-emp="${e.id}">Nonaktifkan</button>`
            : `<button class="btn btn-success btn-sm" data-activate-emp="${e.id}">Aktifkan</button>`}
        </td>
      </tr>`).join('') : `<tr><td colspan="8" class="empty-row">Tidak ada data</td></tr>`}</tbody>
    </table></div>
    <div class="pager">
      <span>Halaman ${pageClamped} dari ${totalPages}</span>
      <button ${pageClamped<=1?'disabled':''} id="empPrevBtn">&larr;</button>
      <button ${pageClamped>=totalPages?'disabled':''} id="empNextBtn">&rarr;</button>
    </div>
  </div>`;
}
function employeeFormHtml(emp){
  const isEdit = !!emp;
  emp = emp || {};
  return `
    <div class="form-row-2">
      <div class="field"><label>Nama Lengkap</label><input type="text" id="fNama" value="${escapeHtml(emp.nama||'')}" required></div>
      <div class="field"><label>Email</label><input type="email" id="fEmail" value="${escapeHtml(emp.email||'')}" required></div>
    </div>
    <div class="form-row-2">
      <div class="field"><label>NIK</label><input type="text" id="fNik" value="${escapeHtml(emp.nik||'')}" required></div>
      <div class="field"><label>Nomor KK</label><input type="text" id="fKk" value="${escapeHtml(emp.kk||'')}" required></div>
    </div>
    <div class="form-row-2">
      <div class="field"><label>No. HP</label><input type="text" id="fHp" value="${escapeHtml(emp.hp||'')}"></div>
      <div class="field"><label>Tempat Lahir</label><input type="text" id="fTempatLahir" value="${escapeHtml(emp.tempatLahir||'')}"></div>
    </div>
    <div class="form-row-2">
      <div class="field"><label>Tanggal Lahir</label><input type="date" id="fTglLahir" value="${emp.tglLahir||''}"></div>
      <div class="field"><label>Alamat</label><input type="text" id="fAlamat" value="${escapeHtml(emp.alamat||'')}"></div>
    </div>
    <div class="divider"></div>
    <div class="form-row-2">
      <div class="field"><label>Tanggal Masuk</label><input type="date" id="fJoinDate" value="${emp.joinDate||''}" required></div>
      <div class="field"><label>Jabatan</label><input type="text" id="fJabatan" value="${escapeHtml(emp.jabatan||'')}" required></div>
    </div>
    <div class="form-row-2">
      <div class="field"><label>Departemen</label><select id="fDepartemen" required><option value="">Pilih departemen</option>${departemenOptionsHtml(emp.departemen||'')}</select></div>
      <div class="field"><label>Atasan</label><input type="text" id="fAtasan" value="${escapeHtml(emp.atasan||'')}"></div>
    </div>
    <div class="field"><label>Jadwal Kerja</label><select id="fJadwalKerja">${jadwalOptionsHtml(getJadwalKerjaKode(emp))}</select></div>
    <div class="divider"></div>
    <div class="form-row-2">
      <div class="field"><label>Gaji Pokok (Rp)</label><input type="number" id="fGajiPokok" min="0" step="1000" value="${emp.gajiPokok||0}"></div>
      <div class="field"><label>Tunjangan Tetap (Rp)</label><input type="number" id="fTunjanganTetap" min="0" step="1000" value="${emp.tunjanganTetap||0}"></div>
    </div>
    <div class="form-row-2">
      <div class="field"><label>Tarif Lembur per Jam (Rp)</label><input type="number" id="fTarifLembur" min="0" step="1000" value="${emp.tarifLemburPerJam||0}"></div>
      <div class="field"><label>Status PTKP (PPh 21)</label>
        <select id="fPtkp">${PTKP_OPTIONS.map(k=>`<option value="${k}" ${(emp.statusPTKP||'TK0')===k?'selected':''}>${ptkpLabel(k)}</option>`).join('')}</select>
      </div>
    </div>
    <div class="field">
      <label><input type="checkbox" id="fIkutBpjsTk" style="width:auto;display:inline-block;margin-right:6px;" ${emp.ikutBpjsTK!==false?'checked':''}>Ikut BPJS Ketenagakerjaan</label>
      <label style="margin-left:18px;"><input type="checkbox" id="fIkutBpjsKesehatan" style="width:auto;display:inline-block;margin-right:6px;" ${emp.ikutBpjsKesehatan?'checked':''}>Ikut BPJS Kesehatan</label>
    </div>
    <div class="form-row-2">
      <div class="field"><label>BPJS TK Karyawan (%) <span class="hint">kosongkan = pakai default</span></label><input type="number" step="0.01" min="0" id="fBpjsTkKaryawan" value="${emp.bpjsTkKaryawanPersen!=null?emp.bpjsTkKaryawanPersen:''}" placeholder="default"></div>
      <div class="field"><label>BPJS TK Perusahaan (%)</label><input type="number" step="0.01" min="0" id="fBpjsTkPerusahaan" value="${emp.bpjsTkPerusahaanPersen!=null?emp.bpjsTkPerusahaanPersen:''}" placeholder="default"></div>
    </div>
    <div class="form-row-2">
      <div class="field"><label>BPJS Kesehatan Karyawan (%)</label><input type="number" step="0.01" min="0" id="fBpjsKesKaryawan" value="${emp.bpjsKesehatanKaryawanPersen!=null?emp.bpjsKesehatanKaryawanPersen:''}" placeholder="default"></div>
      <div class="field"><label>BPJS Kesehatan Perusahaan (%)</label><input type="number" step="0.01" min="0" id="fBpjsKesPerusahaan" value="${emp.bpjsKesehatanPerusahaanPersen!=null?emp.bpjsKesehatanPerusahaanPersen:''}" placeholder="default"></div>
    </div>
    <div class="field"><label>PPh 21 Ditanggung Perusahaan (%) <span class="hint">0 = karyawan tanggung penuh (Gross), 100 = perusahaan tanggung penuh (Nett)</span></label><input type="number" min="0" max="100" id="fPph21Perusahaan" value="${emp.pph21DitanggungPerusahaanPersen||0}"></div>
    <div class="divider"></div>
    <div class="form-row-2">
      <div class="field"><label>Jenis Kontrak</label>
        <select id="fJenisKontrak">
          ${['PKWT','PKWTT','Probation','Magang','Harian/Lepas','Lainnya'].map(j=>`<option value="${j}" ${emp.jenisKontrak===j?'selected':''}>${j}</option>`).join('')}
        </select>
      </div>
      <div class="field"><label>Nomor Kontrak</label><input type="text" id="fNomorKontrak" value="${escapeHtml(emp.nomorKontrak||'')}"></div>
    </div>
    <div class="form-row-2">
      <div class="field"><label>Tanggal Mulai Kontrak</label><input type="date" id="fKontrakMulai" value="${emp.kontrakMulai||''}"></div>
      <div class="field"><label>Tanggal Berakhir Kontrak (kosongkan jika PKWTT)</label><input type="date" id="fKontrakSelesai" value="${emp.kontrakSelesai||''}"></div>
    </div>
    ${!isEdit ? `
    <div class="divider"></div>
    <div class="field"><label><input type="checkbox" id="fCreateLogin" checked style="width:auto;display:inline-block;margin-right:6px;">Buat akun login karyawan sekaligus</label></div>
    <div class="field"><label>Password Awal</label><input type="text" id="fLoginPassword" value="123456"></div>
    ` : ''}
  `;
}
function openEmployeeModal(empId){
  const emp = empId ? DB.employees().find(e => e.id === empId) : null;
  const bg = document.createElement('div');
  bg.className = 'modal-bg';
  bg.innerHTML = `
    <div class="modal">
      <button class="modal-close" id="modalCloseBtn">&times;</button>
      <h3>${emp ? 'Edit Karyawan' : 'Tambah Karyawan'}</h3>
      <form id="empForm">
        ${employeeFormHtml(emp)}
        <button class="btn btn-primary btn-block" type="submit" style="margin-top:8px;">${emp ? 'Simpan Perubahan' : 'Tambah Karyawan'}</button>
      </form>
    </div>`;
  document.body.appendChild(bg);
  document.getElementById('modalCloseBtn').addEventListener('click', () => bg.remove());
  bg.addEventListener('click', e => { if(e.target === bg) bg.remove(); });

  // Saran otomatis (bukan wajib): karyawan baru di Departemen Produksi ditawarin Shift 2 sebagai tebakan awal,
  // HRD tetap bebas ubah ke STAFF atau shift lain.
  if(!emp){
    const deptSel = document.getElementById('fDepartemen');
    const jadwalSel = document.getElementById('fJadwalKerja');
    deptSel.addEventListener('change', () => {
      if(deptSel.value.startsWith('Produksi') && jadwalSel.value === 'STAFF') jadwalSel.value = 'SHIFT2';
    });
  }

  document.getElementById('empForm').addEventListener('submit', e => {
    e.preventDefault();
    const payload = {
      nama: document.getElementById('fNama').value, email: document.getElementById('fEmail').value,
      nik: document.getElementById('fNik').value, kk: document.getElementById('fKk').value,
      hp: document.getElementById('fHp').value, tempatLahir: document.getElementById('fTempatLahir').value,
      tglLahir: document.getElementById('fTglLahir').value, alamat: document.getElementById('fAlamat').value,
      joinDate: document.getElementById('fJoinDate').value, jabatan: document.getElementById('fJabatan').value,
      departemen: document.getElementById('fDepartemen').value, atasan: document.getElementById('fAtasan').value,
      jadwalKerja: document.getElementById('fJadwalKerja').value,
      gajiPokok: Number(document.getElementById('fGajiPokok').value)||0,
      tunjanganTetap: Number(document.getElementById('fTunjanganTetap').value)||0,
      tarifLemburPerJam: Number(document.getElementById('fTarifLembur').value)||0,
      statusPTKP: document.getElementById('fPtkp').value,
      ikutBpjsTK: document.getElementById('fIkutBpjsTk').checked,
      ikutBpjsKesehatan: document.getElementById('fIkutBpjsKesehatan').checked,
      bpjsTkKaryawanPersen: document.getElementById('fBpjsTkKaryawan').value === '' ? null : Number(document.getElementById('fBpjsTkKaryawan').value),
      bpjsTkPerusahaanPersen: document.getElementById('fBpjsTkPerusahaan').value === '' ? null : Number(document.getElementById('fBpjsTkPerusahaan').value),
      bpjsKesehatanKaryawanPersen: document.getElementById('fBpjsKesKaryawan').value === '' ? null : Number(document.getElementById('fBpjsKesKaryawan').value),
      bpjsKesehatanPerusahaanPersen: document.getElementById('fBpjsKesPerusahaan').value === '' ? null : Number(document.getElementById('fBpjsKesPerusahaan').value),
      pph21DitanggungPerusahaanPersen: Number(document.getElementById('fPph21Perusahaan').value)||0,
      jenisKontrak: document.getElementById('fJenisKontrak').value, nomorKontrak: document.getElementById('fNomorKontrak').value,
      kontrakMulai: document.getElementById('fKontrakMulai').value, kontrakSelesai: document.getElementById('fKontrakSelesai').value
    };
    try{
      if(emp){
        updateEmployee(emp.id, payload);
        toast('Data karyawan berhasil diperbarui.', 'success');
      } else {
        const createLogin = document.getElementById('fCreateLogin').checked;
        payload.loginPassword = document.getElementById('fLoginPassword').value;
        createEmployee(payload, createLogin);
        toast('Karyawan baru berhasil ditambahkan.', 'success');
      }
      bg.remove();
      goTo('employees', ROUTE.params);
    }catch(err){ toast(err.message, 'error'); }
  });
}
function openEmployeeViewModal(empId){
  const emp = DB.employees().find(e => e.id === empId);
  if(!emp) return;
  const bg = document.createElement('div');
  bg.className = 'modal-bg';
  bg.innerHTML = `
    <div class="modal">
      <button class="modal-close" id="modalCloseBtn">&times;</button>
      <h3>${escapeHtml(emp.nama)}</h3>
      <div class="kv">
        <div>ID Karyawan</div><div>${escapeHtml(emp.id)}</div>
        <div>NIK</div><div>${escapeHtml(emp.nik)}</div>
        <div>No. KK</div><div>${escapeHtml(emp.kk)}</div>
        <div>Email</div><div>${escapeHtml(emp.email)}</div>
        <div>No. HP</div><div>${escapeHtml(emp.hp)}</div>
        <div>Alamat</div><div>${escapeHtml(emp.alamat)}</div>
        <div>Tempat/Tgl Lahir</div><div>${escapeHtml(emp.tempatLahir)}, ${fmtDate(emp.tglLahir)}</div>
        <div>Tanggal Masuk</div><div>${fmtDate(emp.joinDate)}</div>
        <div>Jabatan</div><div>${escapeHtml(emp.jabatan)}</div>
        <div>Departemen</div><div>${escapeHtml(emp.departemen)}</div>
        <div>Atasan</div><div>${escapeHtml(emp.atasan||'-')}</div>
        <div>Jadwal Kerja</div><div>${(findJadwal(getJadwalKerjaKode(emp))||{}).nama || getJadwalKerjaKode(emp)}</div>
        <div>Status</div><div>${emp.status}</div>
        <div>Jenis Kontrak</div><div>${escapeHtml(emp.jenisKontrak)}</div>
        <div>Nomor Kontrak</div><div>${escapeHtml(emp.nomorKontrak||'-')}</div>
        <div>Mulai Kontrak</div><div>${fmtDate(emp.kontrakMulai)}</div>
        <div>Berakhir Kontrak</div><div>${emp.kontrakSelesai ? fmtDate(emp.kontrakSelesai) : 'Tidak ada (PKWTT)'}</div>
      </div>
    </div>`;
  document.body.appendChild(bg);
  document.getElementById('modalCloseBtn').addEventListener('click', () => bg.remove());
  bg.addEventListener('click', e => { if(e.target === bg) bg.remove(); });
}
function bindEmployeesEvents(){
  const q = document.getElementById('empSearch');
  const dept = document.getElementById('empDeptFilter');
  const status = document.getElementById('empStatusFilter');
  function applyFilters(){ goTo('employees', {q:q.value, dept:dept.value, status:status.value, page:1}); }
  if(q) q.addEventListener('change', applyFilters);
  if(dept) dept.addEventListener('change', applyFilters);
  if(status) status.addEventListener('change', applyFilters);

  const addBtn = document.getElementById('empAddBtn');
  if(addBtn) addBtn.addEventListener('click', () => openEmployeeModal(null));

  const importBtn = document.getElementById('empImportExcelBtn');
  if(importBtn) importBtn.addEventListener('click', () => {
    if(!confirm('Import 103 karyawan dari data Excel komposisi karyawan? Data yang sudah pernah di-import sebelumnya tidak akan dobel.')) return;
    try{
      const jumlah = bulkImportEmployeesFromExcel();
      toast(jumlah + ' karyawan berhasil di-import. Cek & lengkapi jadwal kerja / data lain per karyawan.', 'success');
      goTo('employees', ROUTE.params);
    }catch(err){ toast(err.message, 'error'); }
  });

  document.querySelectorAll('[data-view-emp]').forEach(b => b.addEventListener('click', () => openEmployeeViewModal(b.getAttribute('data-view-emp'))));
  document.querySelectorAll('[data-edit-emp]').forEach(b => b.addEventListener('click', () => openEmployeeModal(b.getAttribute('data-edit-emp'))));
  document.querySelectorAll('[data-deactivate-emp]').forEach(b => b.addEventListener('click', () => {
    try{ setEmployeeStatus(b.getAttribute('data-deactivate-emp'), 'NONAKTIF'); toast('Karyawan dinonaktifkan.', 'success'); goTo('employees', ROUTE.params); }
    catch(err){ toast(err.message, 'error'); }
  }));
  document.querySelectorAll('[data-activate-emp]').forEach(b => b.addEventListener('click', () => {
    try{ setEmployeeStatus(b.getAttribute('data-activate-emp'), 'AKTIF'); toast('Karyawan diaktifkan kembali.', 'success'); goTo('employees', ROUTE.params); }
    catch(err){ toast(err.message, 'error'); }
  }));

  const exportBtn = document.getElementById('empExportBtn');
  if(exportBtn) exportBtn.addEventListener('click', () => {
    const csv = toCSV(DB.employees(), [
      {label:'ID', value:'id'}, {label:'NIK', value:'nik'}, {label:'No KK', value:'kk'}, {label:'Nama', value:'nama'},
      {label:'Email', value:'email'}, {label:'HP', value:'hp'}, {label:'Jabatan', value:'jabatan'}, {label:'Departemen', value:'departemen'},
      {label:'Tanggal Masuk', value:'joinDate'}, {label:'Jenis Kontrak', value:'jenisKontrak'}, {label:'Mulai Kontrak', value:'kontrakMulai'},
      {label:'Berakhir Kontrak', value:'kontrakSelesai'}, {label:'Status', value:'status'}
    ]);
    downloadCSV('data_karyawan.csv', csv);
    writeAudit(currentUser(), 'Export data karyawan', 'CSV', '-', '-');
  });

  const pageParams = ROUTE.params || {};
  const prevBtn = document.getElementById('empPrevBtn');
  const nextBtn = document.getElementById('empNextBtn');
  if(prevBtn) prevBtn.addEventListener('click', () => goTo('employees', Object.assign({}, pageParams, {page:(pageParams.page||1)-1})));
  if(nextBtn) nextBtn.addEventListener('click', () => goTo('employees', Object.assign({}, pageParams, {page:(pageParams.page||1)+1})));
}

/* ---- Contract monitoring page ---- */
function renderContractsPage(){
  const list = DB.employees().map(e => Object.assign({}, e, {contract: contractStatus(e.kontrakSelesai)}))
    .sort((a,b) => (a.contract.sisaHari===null?99999:a.contract.sisaHari) - (b.contract.sisaHari===null?99999:b.contract.sisaHari));
  const summary = contractSummary();
  return `
  <div class="grid grid-4">
    <div class="card stat stat-success"><div class="num">${summary.aktif}</div><div class="label">Aktif</div></div>
    <div class="card stat stat-warning"><div class="num">${summary.w60}</div><div class="label">&le; 60 Hari</div></div>
    <div class="card stat stat-danger"><div class="num">${summary.w30}</div><div class="label">&le; 30 Hari</div></div>
    <div class="card stat stat-danger"><div class="num">${summary.berakhir}</div><div class="label">Sudah Berakhir</div></div>
  </div>
  <div class="panel" style="margin-top:16px;">
    <div class="panel-head"><h3>Daftar Kontrak Karyawan</h3><button class="btn btn-outline btn-sm" id="contractExportBtn">Export CSV</button></div>
    <div class="table-wrap"><table class="datatable">
      <thead><tr><th>Karyawan</th><th>Jenis Kontrak</th><th>Mulai</th><th>Berakhir</th><th>Sisa Hari</th><th>Status</th></tr></thead>
      <tbody>${list.map(e => `<tr>
        <td>${escapeHtml(e.nama)}</td><td>${escapeHtml(e.jenisKontrak)}</td><td>${fmtDate(e.kontrakMulai)}</td>
        <td>${e.kontrakSelesai ? fmtDate(e.kontrakSelesai) : '-'}</td>
        <td>${e.contract.sisaHari===null ? '-' : e.contract.sisaHari + ' hari'}</td>
        <td><span class="badge badge-${e.contract.level}">${e.contract.label}</span></td>
      </tr>`).join('')}</tbody>
    </table></div>
  </div>`;
}
function bindContractsEvents(){
  const btn = document.getElementById('contractExportBtn');
  if(btn) btn.addEventListener('click', () => {
    const list = DB.employees().map(e => Object.assign({}, e, {contract: contractStatus(e.kontrakSelesai)}));
    const csv = toCSV(list, [
      {label:'Nama', value:'nama'}, {label:'Jenis Kontrak', value:'jenisKontrak'}, {label:'Mulai', value:'kontrakMulai'},
      {label:'Berakhir', value:'kontrakSelesai'}, {label:'Sisa Hari', value: r => r.contract.sisaHari}, {label:'Status', value: r => r.contract.label}
    ]);
    downloadCSV('monitoring_kontrak.csv', csv);
    writeAudit(currentUser(), 'Export monitoring kontrak', 'CSV', '-', '-');
  });
}

/* ---- Attendance (all employees) page ---- */
function renderAttendanceAllPage(){
  const p = ROUTE.params || {};
  const tanggal = p.tanggal || todayISO();
  const dept = p.dept || '';
  const empId = p.emp || '';

  let list = DB.attendance().filter(a => a.tanggal === tanggal);
  const employees = DB.employees();
  if(dept) list = list.filter(a => { const e = employees.find(x=>x.id===a.employeeId); return e && e.departemen === dept; });
  if(empId) list = list.filter(a => a.employeeId === empId);

  const depts = [...new Set(employees.map(e => e.departemen))];

  return `
  <div class="panel">
    <div class="panel-head">
      <h3>Absensi Semua Karyawan</h3>
      <div class="toolbar">
        <input type="date" id="attTanggal" value="${tanggal}">
        <select id="attDept"><option value="">Semua Departemen</option>${depts.map(d=>`<option value="${escapeHtml(d)}" ${dept===d?'selected':''}>${escapeHtml(d)}</option>`).join('')}</select>
        <button class="btn btn-outline btn-sm" id="attExportBtn">Export CSV</button>
      </div>
    </div>
    <div class="table-wrap"><table class="datatable">
      <thead><tr><th>Nama</th><th>Departemen</th><th>Masuk</th><th>Pulang</th><th>Status</th><th>Jarak Masuk</th><th>Akurasi Masuk</th></tr></thead>
      <tbody>${list.length ? list.map(a => {
        const e = employees.find(x=>x.id===a.employeeId);
        return `<tr>
        <td>${escapeHtml(a.nama)}</td><td>${escapeHtml(e?e.departemen:'-')}</td>
        <td>${a.jamMasuk||'-'}</td><td>${a.jamPulang||'-'}</td><td>${statusBadge(a.statusMasuk)}${a.statusPulang==='PULANG_CEPAT_PERLU_IZIN' ? ' '+statusBadge(a.statusPulang) : ''}</td>
        <td>${a.jarakMasuk!=null ? a.jarakMasuk+' m':'-'}</td><td>${a.accMasuk!=null ? '&plusmn;'+Math.round(a.accMasuk)+' m':'-'}</td>
      </tr>`;}).join('') : `<tr><td colspan="7" class="empty-row">Tidak ada data absensi pada tanggal ini</td></tr>`}</tbody>
    </table></div>
  </div>`;
}
function bindAttendanceAllEvents(){
  const tgl = document.getElementById('attTanggal');
  const dept = document.getElementById('attDept');
  function apply(){ goTo('attendance-all', {tanggal: tgl.value, dept: dept.value}); }
  if(tgl) tgl.addEventListener('change', apply);
  if(dept) dept.addEventListener('change', apply);
  const exportBtn = document.getElementById('attExportBtn');
  if(exportBtn) exportBtn.addEventListener('click', () => {
    const p = ROUTE.params || {};
    const tanggal = p.tanggal || todayISO();
    const list = DB.attendance().filter(a => a.tanggal === tanggal);
    const csv = toCSV(list, [
      {label:'Nama', value:'nama'}, {label:'Tanggal', value:'tanggal'}, {label:'Jam Masuk', value:'jamMasuk'},
      {label:'Jam Pulang', value:'jamPulang'}, {label:'Status', value:'statusMasuk'}, {label:'Jarak Masuk (m)', value:'jarakMasuk'},
      {label:'Akurasi Masuk (m)', value:'accMasuk'}, {label:'Jarak Pulang (m)', value:'jarakPulang'}, {label:'Akurasi Pulang (m)', value:'accPulang'}
    ]);
    downloadCSV('absensi_' + tanggal + '.csv', csv);
    writeAudit(currentUser(), 'Export absensi', tanggal, '-', '-');
  });
}

/* ---- Overtime recap page ---- */
function renderOvertimeRecapPage(){
  const p = ROUTE.params || {};
  const bulan = p.bulan || todayISO().slice(0,7);
  const dept = p.dept || '';
  const employees = DB.employees();
  let list = DB.overtimeRequests().filter(r => r.status === 'DISETUJUI' && r.tanggal.startsWith(bulan));
  if(dept) list = list.filter(r => { const e = employees.find(x=>x.id===r.employeeId); return e && e.departemen === dept; });

  const byEmp = {};
  list.forEach(r => {
    byEmp[r.employeeId] = byEmp[r.employeeId] || {nama:r.nama, totalJam:0};
    byEmp[r.employeeId].totalJam += r.totalJam;
  });
  const rows = Object.values(byEmp).sort((a,b)=>b.totalJam-a.totalJam);
  const depts = [...new Set(employees.map(e => e.departemen))];

  return `
  <div class="panel">
    <div class="panel-head">
      <h3>Rekap Lembur</h3>
      <div class="toolbar">
        <input type="month" id="recapBulan" value="${bulan}">
        <select id="recapDept"><option value="">Semua Departemen</option>${depts.map(d=>`<option value="${escapeHtml(d)}" ${dept===d?'selected':''}>${escapeHtml(d)}</option>`).join('')}</select>
        <button class="btn btn-outline btn-sm" id="recapExportBtn">Export CSV</button>
      </div>
    </div>
    <div class="table-wrap"><table class="datatable">
      <thead><tr><th>Karyawan</th><th>Bulan</th><th class="right">Total Jam</th></tr></thead>
      <tbody>${rows.length ? rows.map(r => `<tr><td>${escapeHtml(r.nama)}</td><td>${bulan}</td><td class="right tabular">${r.totalJam}</td></tr>`).join('')
        : `<tr><td colspan="3" class="empty-row">Tidak ada data lembur disetujui pada bulan ini</td></tr>`}</tbody>
    </table></div>
  </div>`;
}
function bindOvertimeRecapEvents(){
  const bulan = document.getElementById('recapBulan');
  const dept = document.getElementById('recapDept');
  function apply(){ goTo('overtime-recap', {bulan: bulan.value, dept: dept.value}); }
  if(bulan) bulan.addEventListener('change', apply);
  if(dept) dept.addEventListener('change', apply);
  const exportBtn = document.getElementById('recapExportBtn');
  if(exportBtn) exportBtn.addEventListener('click', () => {
    const p = ROUTE.params || {};
    const bulan = p.bulan || todayISO().slice(0,7);
    const employees = DB.employees();
    let list = DB.overtimeRequests().filter(r => r.status === 'DISETUJUI' && r.tanggal.startsWith(bulan));
    const byEmp = {};
    list.forEach(r => { byEmp[r.employeeId] = byEmp[r.employeeId] || {nama:r.nama, totalJam:0}; byEmp[r.employeeId].totalJam += r.totalJam; });
    const rows = Object.values(byEmp);
    const csv = toCSV(rows, [{label:'Karyawan', value:'nama'}, {label:'Bulan', value:()=>bulan}, {label:'Total Jam', value:'totalJam'}]);
    downloadCSV('rekap_lembur_' + bulan + '.csv', csv);
    writeAudit(currentUser(), 'Export rekap lembur', bulan, '-', '-');
  });
}

/* ---- Roster shift mingguan (khusus operator shift) ---- */
function mondayOf(dateStr){
  const d = new Date(dateStr + 'T00:00:00');
  const day = d.getDay();
  const diff = day === 0 ? -6 : 1 - day;
  d.setDate(d.getDate() + diff);
  return d.toISOString().slice(0,10);
}
function addDaysStr(dateStr, n){
  const d = new Date(dateStr + 'T00:00:00');
  d.setDate(d.getDate() + n);
  return d.toISOString().slice(0,10);
}
function renderRosterShiftPage(){
  const p = ROUTE.params || {};
  const minggu = mondayOf(p.minggu || todayISO());
  const days = [0,1,2,3,4,5,6].map(i => addDaysStr(minggu, i));
  const dayLabels = ['Sen','Sel','Rab','Kam','Jum','Sab','Min'];
  const rosterKodes = jadwalKerjaList().filter(j => j.bisaRoster).map(j => j.kode);
  const employees = DB.employees().filter(e => e.status === 'AKTIF' && rosterKodes.includes(getJadwalKerjaKode(e)));
  const rosterEntries = DB.rosterShift();

  return `
  <div class="toolbar" style="margin-bottom:14px;">
    <button class="btn btn-outline btn-sm" id="rosterPrevWeek">&laquo; Minggu Sebelumnya</button>
    <span class="small muted">${fmtDate(days[0])} - ${fmtDate(days[6])}</span>
    <button class="btn btn-outline btn-sm" id="rosterNextWeek">Minggu Berikutnya &raquo;</button>
  </div>
  ${employees.length ? `
  <div class="panel">
    <div class="table-wrap"><table class="datatable">
      <thead><tr><th>Nama</th><th>Jadwal Default</th>${days.map((d,i)=>`<th>${dayLabels[i]}<br><span class="small muted">${d.slice(5)}</span></th>`).join('')}</tr></thead>
      <tbody>${employees.map(e => {
        const defKode = getJadwalKerjaKode(e);
        return `<tr><td>${escapeHtml(e.nama)}</td><td class="small">${escapeHtml((findJadwal(defKode)||{}).nama||defKode)}</td>
        ${days.map(d => {
          const existing = rosterEntries.find(r => r.employeeId === e.id && r.tanggal === d);
          return `<td><select data-roster-emp="${e.id}" data-roster-date="${d}" data-roster-nama="${escapeHtml(e.nama)}">
            <option value="">(default)</option>
            ${rosterKodes.map(k => `<option value="${k}" ${existing&&existing.shiftKode===k?'selected':''}>${k}</option>`).join('')}
          </select></td>`;
        }).join('')}</tr>`;
      }).join('')}</tbody>
    </table></div>
    <div class="panel-body"><button class="btn btn-primary btn-sm" id="rosterSaveBtn">Simpan Roster Minggu Ini</button></div>
  </div>
  ` : `<div class="card"><p class="muted mt-0">Belum ada karyawan dengan Jadwal Kerja shift (SHIFT1/2/3). Atur Jadwal Kerja karyawan operator dulu di halaman Data Karyawan &mdash; karyawan dengan Jadwal Kerja "Staff Reguler" tidak muncul di sini.</p></div>`}
  `;
}
function bindRosterShiftEvents(){
  const p = ROUTE.params || {};
  const minggu = mondayOf(p.minggu || todayISO());
  const prevBtn = document.getElementById('rosterPrevWeek');
  if(prevBtn) prevBtn.addEventListener('click', () => goTo('roster-shift', {minggu: addDaysStr(minggu, -7)}));
  const nextBtn = document.getElementById('rosterNextWeek');
  if(nextBtn) nextBtn.addEventListener('click', () => goTo('roster-shift', {minggu: addDaysStr(minggu, 7)}));

  const saveBtn = document.getElementById('rosterSaveBtn');
  if(saveBtn) saveBtn.addEventListener('click', () => {
    const entries = [];
    document.querySelectorAll('[data-roster-emp]').forEach(sel => {
      entries.push({
        employeeId: sel.getAttribute('data-roster-emp'),
        nama: sel.getAttribute('data-roster-nama'),
        tanggal: sel.getAttribute('data-roster-date'),
        shiftKode: sel.value
      });
    });
    try{
      saveRosterShift(entries);
      toast('Roster shift minggu ini berhasil disimpan.', 'success');
      goTo('roster-shift', {minggu});
    }catch(err){ toast(err.message, 'error'); }
  });
}

/* ---- Payroll page ---- */
function fmtRupiah(n){
  return 'Rp' + Math.round(Number(n)||0).toLocaleString('id-ID');
}
function renderPayrollPage(){
  const p = ROUTE.params || {};
  const tab = p.tab || 'slip';
  const bulan = p.bulan || todayISO().slice(0,7);

  return `
  <div class="pill-nav">
    <button data-paytab="slip" class="${tab==='slip'?'active':''}">Slip Gaji</button>
    <button data-paytab="kehadiran" class="${tab==='kehadiran'?'active':''}">Laporan Kehadiran untuk Payroll</button>
  </div>
  ${tab === 'kehadiran' ? renderPayrollAttendanceReport(bulan) : renderPayrollSlipTab(bulan)}
  `;
}
function renderPayrollSlipTab(bulan){
  const rows = DB.payrollRuns().filter(r => r.periode === bulan).sort((a,b)=>a.nama.localeCompare(b.nama));
  const totalBersih = rows.reduce((s,r)=>s+r.gajiBersih,0);

  return `
  <div class="panel-head" style="background:transparent;border:none;padding:0 0 14px 0;">
    <div class="toolbar">
      <input type="month" id="payBulan" value="${bulan}">
      <button class="btn btn-primary btn-sm" id="payGenerateBtn">${rows.length ? 'Generate Ulang' : 'Generate Payroll Bulan Ini'}</button>
      ${rows.length ? `<button class="btn btn-outline btn-sm" id="payExportBtn">Export CSV</button>` : ''}
    </div>
  </div>

  ${rows.length ? `
  <div class="grid grid-3" style="margin-bottom:16px;">
    <div class="card stat stat-navy"><div class="num">${rows.length}</div><div class="label">Karyawan Digaji</div></div>
    <div class="card stat stat-success"><div class="num" style="font-size:1.3rem;">${fmtRupiah(totalBersih)}</div><div class="label">Total Gaji Bersih Dibayarkan</div></div>
    <div class="card stat stat-warning"><div class="num">${fmtDate(bulan+'-01').slice(3)}</div><div class="label">Periode</div></div>
  </div>
  <div class="panel">
    <div class="table-wrap"><table class="datatable">
      <thead><tr><th>Nama</th><th>Jabatan</th><th>Pokok+Tunjangan</th><th>Lembur</th><th>Potongan Pulang Cepat</th><th>BPJS (Karyawan)</th><th>PPh 21 (Karyawan)</th><th>Gaji Bersih</th><th>Aksi</th></tr></thead>
      <tbody>${rows.map(r => `<tr>
        <td>${escapeHtml(r.nama)}</td><td class="small">${escapeHtml(r.jabatan||'-')}</td>
        <td>${fmtRupiah(r.gajiPokok+r.tunjanganTetap)}</td>
        <td>${fmtRupiah(r.uangLembur)}<div class="small muted">${r.jamLembur} jam</div></td>
        <td>${fmtRupiah(r.potonganTelat)}<div class="small muted">${r.hariTelat} hari</div></td>
        <td>${fmtRupiah(r.bpjsTkKaryawan+r.bpjsKesKaryawan)}<div class="small muted">${r.ikutBpjsTK?'TK':''}${r.ikutBpjsTK&&r.ikutBpjsKesehatan?' + ':''}${r.ikutBpjsKesehatan?'Kes':''}${!r.ikutBpjsTK&&!r.ikutBpjsKesehatan?'-':''}</div></td>
        <td>${fmtRupiah(r.pph21Karyawan)}${r.pph21Perusahaan?`<div class="small muted">Perusahaan: ${fmtRupiah(r.pph21Perusahaan)}</div>`:''}</td>
        <td><b>${fmtRupiah(r.gajiBersih)}</b></td>
        <td><button class="btn btn-outline btn-sm" data-slip="${r.id}">Lihat Slip</button></td>
      </tr>`).join('')}</tbody>
    </table></div>
  </div>
  <p class="hint">PPh 21 dihitung otomatis pakai estimasi tarif progresif tahunan berdasarkan Status PTKP karyawan &mdash; sebaiknya tetap diverifikasi ulang sebelum dipakai sebagai angka final.</p>
  ` : `<div class="card"><p class="muted mt-0">Belum ada payroll untuk periode ini. Klik "Generate Payroll Bulan Ini" untuk menghitung otomatis dari data Gaji Pokok, Tunjangan, Lembur (disetujui), dan Absensi bulan ini.</p></div>`}
  `;
}
// Laporan murni rekap KEHADIRAN untuk bantu proses payroll - TIDAK ada nominal gaji/insentif/pajak
// sama sekali di sini, cuma statistik kehadiran per karyawan per bulan.
function renderPayrollAttendanceReport(bulan){
  const employees = DB.employees().filter(e => e.status === 'AKTIF').sort((a,b)=>a.nama.localeCompare(b.nama));
  const attendance = DB.attendance().filter(a => a.tanggal.startsWith(bulan));
  const leave = DB.leaveRequests().filter(r => r.status === 'DISETUJUI' && r.tglMulai.startsWith(bulan));
  const permission = DB.permissionRequests().filter(r => r.status === 'DISETUJUI' && r.tanggal.startsWith(bulan));

  const rows = employees.map(emp => {
    const attEmp = attendance.filter(a => a.employeeId === emp.id);
    const hariKerjaEfektif = attEmp.length; // jumlah hari kerja terjadwal bulan ini (hadir + alpha, hari libur tidak masuk hitungan)
    const hadir = attEmp.filter(a => a.statusMasuk === 'HADIR').length;
    const alpha = attEmp.filter(a => a.statusMasuk === 'ALPHA').length;
    const pulangCepat = attEmp.filter(a => a.statusPulang === 'PULANG_CEPAT_PERLU_IZIN').length;
    const totalJamKerja = attEmp.reduce((s,a) => s + (a.jamKerjaTotal||0), 0);
    const izin = permission.filter(r => r.employeeId === emp.id).length;
    const cuti = leave.filter(r => r.employeeId === emp.id).length;
    return { emp, hariKerjaEfektif, hadir, alpha, pulangCepat, totalJamKerja: Math.round(totalJamKerja*10)/10, izin, cuti };
  });

  return `
  <div class="panel-head" style="background:transparent;border:none;padding:0 0 14px 0;">
    <div class="toolbar">
      <input type="month" id="payAttBulan" value="${bulan}">
      <button class="btn btn-outline btn-sm" id="payAttExportBtn">Export CSV</button>
    </div>
  </div>
  <div class="panel">
    <div class="table-wrap"><table class="datatable">
      <thead><tr><th>Nama</th><th>Jabatan</th><th>Departemen</th><th>Hari Kerja Efektif</th><th>Hadir</th><th>Izin</th><th>Cuti</th><th>Alpha</th><th>Pulang Cepat (&lt;5 jam)</th><th>Total Jam Kerja</th></tr></thead>
      <tbody>${rows.length ? rows.map(r => `<tr>
        <td>${escapeHtml(r.emp.nama)}</td><td class="small">${escapeHtml(r.emp.jabatan||'-')}</td><td class="small">${escapeHtml(r.emp.departemen||'-')}</td>
        <td>${r.hariKerjaEfektif}</td><td>${r.hadir}</td><td>${r.izin}</td><td>${r.cuti}</td>
        <td>${r.alpha ? `<span class="badge badge-danger">${r.alpha}</span>` : '0'}</td>
        <td>${r.pulangCepat ? `<span class="badge badge-warning">${r.pulangCepat}</span>` : '0'}</td>
        <td>${r.totalJamKerja} jam</td>
      </tr>`).join('') : `<tr><td colspan="10" class="empty-row">Tidak ada data</td></tr>`}</tbody>
    </table></div>
  </div>
  <p class="hint">Laporan ini murni rekap kehadiran (bukan slip gaji) - dipakai tim finance sebagai bahan referensi, bukan angka gaji final.</p>
  `;
}
function payslipHtml(r, settings){
  return `<!DOCTYPE html><html><head><meta charset="utf-8"><title>Slip Gaji - ${escapeHtml(r.nama)} - ${r.periode}</title>
  <style>
    body{font-family:Arial,Helvetica,sans-serif;color:#222;padding:30px;max-width:600px;margin:0 auto;}
    h2{margin:0 0 2px 0;} .muted{color:#777;font-size:0.85rem;}
    table{width:100%;border-collapse:collapse;margin-top:16px;}
    td{padding:6px 0;border-bottom:1px solid #eee;font-size:0.92rem;}
    td.r{text-align:right;}
    .total-row td{border-top:2px solid #333;border-bottom:none;font-weight:bold;padding-top:10px;}
    .section{margin-top:18px;font-weight:bold;color:#A8642A;}
    .header{border-bottom:2px solid #A8642A;padding-bottom:10px;margin-bottom:10px;}
  </style></head><body>
    <div class="header">
      <h2>${escapeHtml(settings.companyName)}</h2>
      <div class="muted">SLIP GAJI &mdash; Periode ${escapeHtml(r.periode)}</div>
    </div>
    <table>
      <tr><td>Nama</td><td class="r">${escapeHtml(r.nama)}</td></tr>
      <tr><td>Jabatan</td><td class="r">${escapeHtml(r.jabatan||'-')}</td></tr>
      <tr><td>Departemen</td><td class="r">${escapeHtml(r.departemen||'-')}</td></tr>
      <tr><td>Status PTKP</td><td class="r">${ptkpLabel(r.ptkp)}</td></tr>
    </table>
    <div class="section">Pendapatan</div>
    <table>
      <tr><td>Gaji Pokok</td><td class="r">${fmtRupiah(r.gajiPokok)}</td></tr>
      <tr><td>Tunjangan Tetap</td><td class="r">${fmtRupiah(r.tunjanganTetap)}</td></tr>
      <tr><td>Uang Lembur (${r.jamLembur} jam)</td><td class="r">${fmtRupiah(r.uangLembur)}</td></tr>
      <tr class="total-row"><td>Total Pendapatan (Bruto)</td><td class="r">${fmtRupiah(r.bruto)}</td></tr>
    </table>
    <div class="section">Potongan</div>
    <table>
      <tr><td>Potongan Pulang Cepat (${r.hariTelat} hari, &lt;5 jam kerja tanpa izin)</td><td class="r">${fmtRupiah(r.potonganTelat)}</td></tr>
      ${r.ikutBpjsTK ? `<tr><td>BPJS Ketenagakerjaan (Karyawan)</td><td class="r">${fmtRupiah(r.bpjsTkKaryawan)}</td></tr>` : ''}
      ${r.ikutBpjsKesehatan ? `<tr><td>BPJS Kesehatan (Karyawan)</td><td class="r">${fmtRupiah(r.bpjsKesKaryawan)}</td></tr>` : ''}
      <tr><td>PPh 21 (estimasi, ditanggung karyawan)</td><td class="r">${fmtRupiah(r.pph21Karyawan)}</td></tr>
      <tr class="total-row"><td>Total Potongan</td><td class="r">${fmtRupiah(r.totalPotongan)}</td></tr>
    </table>
    <table>
      <tr class="total-row" style="font-size:1.15rem;"><td>GAJI BERSIH DITERIMA</td><td class="r">${fmtRupiah(r.gajiBersih)}</td></tr>
    </table>
    <p class="muted" style="margin-top:24px;">
    ${r.ikutBpjsTK?`Iuran BPJS Ketenagakerjaan oleh perusahaan: ${fmtRupiah(r.bpjsTkPerusahaan)}.<br>`:''}
    ${r.ikutBpjsKesehatan?`Iuran BPJS Kesehatan oleh perusahaan: ${fmtRupiah(r.bpjsKesPerusahaan)}.<br>`:''}
    ${r.pph21Perusahaan?`PPh 21 ditanggung perusahaan: ${fmtRupiah(r.pph21Perusahaan)} (tidak memotong gaji karyawan).<br>`:''}
    Dokumen dibuat otomatis oleh sistem pada ${fmtDate(todayISO())}. PPh 21 merupakan estimasi progresif tahunan sederhana.</p>
  </body></html>`;
}
function showPayslip(payrollId){
  const r = DB.payrollRuns().find(x => x.id === payrollId);
  if(!r) return;
  const settings = DB.officeSettings();
  const win = window.open('', '_blank');
  win.document.write(payslipHtml(r, settings));
  win.document.close();
  setTimeout(() => { try{ win.focus(); win.print(); }catch(e){} }, 300);
}
function bindPayrollEvents(){
  const tab = (ROUTE.params && ROUTE.params.tab) || 'slip';
  document.querySelectorAll('[data-paytab]').forEach(b => {
    b.addEventListener('click', () => goTo('payroll', {tab: b.getAttribute('data-paytab')}));
  });

  const bulanInput = document.getElementById('payBulan');
  if(bulanInput) bulanInput.addEventListener('change', () => goTo('payroll', {tab, bulan: bulanInput.value}));

  const genBtn = document.getElementById('payGenerateBtn');
  if(genBtn) genBtn.addEventListener('click', () => {
    const bulan = (document.getElementById('payBulan')||{}).value || todayISO().slice(0,7);
    try{
      const results = generatePayroll(bulan);
      toast('Payroll untuk ' + results.length + ' karyawan berhasil dibuat.', 'success');
      goTo('payroll', {tab:'slip', bulan});
    }catch(err){ toast(err.message, 'error'); }
  });

  document.querySelectorAll('[data-slip]').forEach(b => {
    b.addEventListener('click', () => showPayslip(b.getAttribute('data-slip')));
  });

  const exportBtn = document.getElementById('payExportBtn');
  if(exportBtn) exportBtn.addEventListener('click', () => {
    const bulan = (document.getElementById('payBulan')||{}).value || todayISO().slice(0,7);
    const rows = DB.payrollRuns().filter(r => r.periode === bulan);
    const csv = toCSV(rows, [
      {label:'Nama', value:'nama'}, {label:'Jabatan', value:'jabatan'}, {label:'Departemen', value:'departemen'},
      {label:'Gaji Pokok', value:'gajiPokok'}, {label:'Tunjangan Tetap', value:'tunjanganTetap'},
      {label:'Jam Lembur', value:'jamLembur'}, {label:'Uang Lembur', value:'uangLembur'},
      {label:'Hari Pulang Cepat', value:'hariTelat'}, {label:'Potongan Pulang Cepat', value:'potonganTelat'},
      {label:'BPJS TK Karyawan', value:'bpjsTkKaryawan'}, {label:'BPJS Kesehatan Karyawan', value:'bpjsKesKaryawan'},
      {label:'PPh 21 Karyawan', value:'pph21Karyawan'}, {label:'PPh 21 Perusahaan', value:'pph21Perusahaan'},
      {label:'Total Bruto', value:'bruto'}, {label:'Total Potongan', value:'totalPotongan'}, {label:'Gaji Bersih', value:'gajiBersih'}
    ]);
    downloadCSV('payroll_' + bulan + '.csv', csv);
    writeAudit(currentUser(), 'Export payroll', bulan, '-', '-');
  });

  const attBulanInput = document.getElementById('payAttBulan');
  if(attBulanInput) attBulanInput.addEventListener('change', () => goTo('payroll', {tab:'kehadiran', bulan: attBulanInput.value}));

  const attExportBtn = document.getElementById('payAttExportBtn');
  if(attExportBtn) attExportBtn.addEventListener('click', () => {
    const bulan = (document.getElementById('payAttBulan')||{}).value || todayISO().slice(0,7);
    const employees = DB.employees().filter(e => e.status === 'AKTIF');
    const attendance = DB.attendance().filter(a => a.tanggal.startsWith(bulan));
    const leave = DB.leaveRequests().filter(r => r.status === 'DISETUJUI' && r.tglMulai.startsWith(bulan));
    const permission = DB.permissionRequests().filter(r => r.status === 'DISETUJUI' && r.tanggal.startsWith(bulan));
    const rows = employees.map(emp => {
      const attEmp = attendance.filter(a => a.employeeId === emp.id);
      return {
        nama: emp.nama, jabatan: emp.jabatan, departemen: emp.departemen,
        hariKerjaEfektif: attEmp.length,
        hadir: attEmp.filter(a => a.statusMasuk === 'HADIR').length,
        izin: permission.filter(r => r.employeeId === emp.id).length,
        cuti: leave.filter(r => r.employeeId === emp.id).length,
        alpha: attEmp.filter(a => a.statusMasuk === 'ALPHA').length,
        pulangCepat: attEmp.filter(a => a.statusPulang === 'PULANG_CEPAT_PERLU_IZIN').length,
        totalJamKerja: Math.round(attEmp.reduce((s,a)=>s+(a.jamKerjaTotal||0),0)*10)/10
      };
    });
    const csv = toCSV(rows, [
      {label:'Nama', value:'nama'}, {label:'Jabatan', value:'jabatan'}, {label:'Departemen', value:'departemen'},
      {label:'Hari Kerja Efektif', value:'hariKerjaEfektif'}, {label:'Hadir', value:'hadir'},
      {label:'Izin', value:'izin'}, {label:'Cuti', value:'cuti'}, {label:'Alpha', value:'alpha'},
      {label:'Pulang Cepat', value:'pulangCepat'}, {label:'Total Jam Kerja', value:'totalJamKerja'}
    ]);
    downloadCSV('laporan_kehadiran_payroll_' + bulan + '.csv', csv);
    writeAudit(currentUser(), 'Export laporan kehadiran payroll', bulan, '-', '-');
  });
}

/* ---- Office settings page ---- */
function renderSettingsPage(){
  const s = DB.officeSettings();
  const leaveTypes = DB.leaveTypes();
  const users = DB.users();
  const employees = DB.employees();
  const tab = (ROUTE.params && ROUTE.params.tab) || 'kantor';

  return `
  <div class="pill-nav">
    <button data-settab="kantor" class="${tab==='kantor'?'active':''}">Pengaturan Kantor</button>
    <button data-settab="jadwal" class="${tab==='jadwal'?'active':''}">Jadwal Kerja</button>
    <button data-settab="cuti" class="${tab==='cuti'?'active':''}">Jenis Cuti</button>
    <button data-settab="users" class="${tab==='users'?'active':''}">Kelola User</button>
  </div>

  ${tab === 'kantor' ? `
  <div class="panel">
    <div class="panel-head"><h3>Pengaturan Kantor</h3></div>
    <div class="panel-body">
      <form id="settingsForm">
        <div class="field"><label>Nama Perusahaan</label><input type="text" id="sNama" value="${escapeHtml(s.companyName)}" required></div>
        <div class="form-row-2">
          <div class="field"><label>Latitude Kantor</label><input type="text" id="sLat" value="${s.lat}" required></div>
          <div class="field"><label>Longitude Kantor</label><input type="text" id="sLng" value="${s.lng}" required></div>
        </div>
        <div class="form-row-2">
          <div class="field"><label>Radius Absensi (meter)</label><input type="number" id="sRadius" value="${s.radius}" required></div>
          <div class="field"><label>Batas Keterlambatan (menit toleransi)</label><input type="number" id="sBatas" value="${s.batasKeterlambatan||0}"></div>
        </div>
        <div class="form-row-2">
          <div class="field"><label>Jam Masuk</label><input type="time" id="sJamMasuk" value="${s.jamMasuk}" required></div>
          <div class="field"><label>Jam Pulang</label><input type="time" id="sJamPulang" value="${s.jamPulang}" required></div>
        </div>
        <div class="divider"></div>
        <div class="form-row-2">
          <div class="field"><label>BPJS TK - Potongan Karyawan (%)</label><input type="number" step="0.01" min="0" id="sBpjsKaryawan" value="${s.bpjsTkKaryawanPersen||0}"></div>
          <div class="field"><label>BPJS TK - Iuran Perusahaan (%)</label><input type="number" step="0.01" min="0" id="sBpjsPerusahaan" value="${s.bpjsTkPerusahaanPersen||0}"></div>
        </div>
        <div class="form-row-2">
          <div class="field"><label>BPJS Kesehatan - Potongan Karyawan (%)</label><input type="number" step="0.01" min="0" id="sBpjsKesKaryawan" value="${s.bpjsKesehatanKaryawanPersen||0}"></div>
          <div class="field"><label>BPJS Kesehatan - Iuran Perusahaan (%)</label><input type="number" step="0.01" min="0" id="sBpjsKesPerusahaan" value="${s.bpjsKesehatanPerusahaanPersen||0}"></div>
        </div>
        <p class="hint">Ini nilai default. Tiap karyawan bisa punya persentase sendiri (override) di halaman Data Karyawan, sesuai perjanjian kontrak masing-masing.</p>
        <div class="field"><label>Potongan Pulang Cepat per Hari (Rp)</label><p class="hint">Dipotong kalau karyawan pulang dengan total jam kerja di bawah 5 jam tanpa izin HR.</p><input type="number" min="0" step="1000" id="sPotonganTelat" value="${s.potonganTelatPerHari||0}"></div>
        <div class="field"><label>Sistem Absensi Mulai Dipakai Sejak</label><input type="date" id="sTanggalMulai" value="${s.tanggalMulaiAbsensi||todayISO()}"></div>
        <p class="hint">Deteksi Alpha tidak akan pernah mundur melewati tanggal ini, berapa pun lama karyawan sudah bergabung sebelumnya.</p>
        <button class="btn btn-primary" type="submit">Simpan Pengaturan</button>
      </form>
      <p class="hint">Untuk mengganti lokasi kantor, cukup ubah nilai Latitude/Longitude di atas lalu simpan &mdash; tidak perlu mengubah kode program.</p>
    </div>
  </div>` : ''}

  ${tab === 'jadwal' ? `
  <div class="panel" style="margin-bottom:16px;">
    <div class="panel-head"><h3>${(ROUTE.params&&ROUTE.params.editJadwal) ? 'Edit Jadwal' : 'Tambah Jadwal Kerja Baru'}</h3></div>
    <div class="panel-body">
      ${(() => {
        const editKode = ROUTE.params && ROUTE.params.editJadwal;
        const j = editKode ? (findJadwal(editKode)||{}) : {};
        return `
        <form id="jadwalForm">
          <div class="form-row-2">
            <div class="field"><label>Kode</label><input type="text" id="jKode" value="${escapeHtml(j.kode||'')}" ${editKode?'readonly':''} placeholder="mis. SHIFT4" required></div>
            <div class="field"><label>Nama Jadwal</label><input type="text" id="jNama" value="${escapeHtml(j.nama||'')}" required></div>
          </div>
          <div class="form-row-2">
            <div class="field"><label>Jam Masuk (Senin-Jumat/default)</label><input type="time" id="jJamMasuk" value="${j.jamMasuk||''}" required></div>
            <div class="field"><label>Jam Pulang</label><input type="time" id="jJamPulang" value="${j.jamPulang||''}" required></div>
          </div>
          <div class="form-row-2">
            <div class="field"><label>Jam Masuk Sabtu (opsional, beda dari hari biasa)</label><input type="time" id="jJamMasukSabtu" value="${j.jamMasukSabtu||''}"></div>
            <div class="field"><label>Jam Pulang Sabtu</label><input type="time" id="jJamPulangSabtu" value="${j.jamPulangSabtu||''}"></div>
          </div>
          <div class="field">
            <label><input type="checkbox" id="jKerjaSabtu" style="width:auto;display:inline-block;margin-right:6px;" ${j.kerjaSabtu?'checked':''}>Hari Sabtu tetap kerja (kalau jam Sabtu di atas dikosongkan, pakai jam biasa)</label>
          </div>
          <div class="field">
            <label><input type="checkbox" id="jOvernight" style="width:auto;display:inline-block;margin-right:6px;" ${j.overnight?'checked':''}>Jadwal melewati tengah malam (jam pulang di hari berikutnya)</label>
          </div>
          <div class="field">
            <label><input type="checkbox" id="jBisaRoster" style="width:auto;display:inline-block;margin-right:6px;" ${j.bisaRoster?'checked':''}>Ikut Roster Shift Mingguan (khusus jadwal shift operator)</label>
          </div>
          <button class="btn btn-primary btn-sm" type="submit">${editKode?'Simpan Perubahan':'Tambah Jadwal'}</button>
          ${editKode ? `<button class="btn btn-outline btn-sm" type="button" id="jadwalCancelBtn">Batal</button>` : ''}
        </form>`;
      })()}
    </div>
  </div>
  <div class="panel">
    <div class="panel-head"><h3>Daftar Jadwal Kerja</h3></div>
    <div class="table-wrap"><table class="datatable">
      <thead><tr><th>Kode</th><th>Nama</th><th>Jam (Senin-Jumat)</th><th>Jam Sabtu</th><th>Roster?</th><th>Aksi</th></tr></thead>
      <tbody>${jadwalKerjaList().map(j => `<tr>
        <td>${escapeHtml(j.kode)}</td><td>${escapeHtml(j.nama)}</td>
        <td>${j.jamMasuk} - ${j.jamPulang}${j.overnight?' <span class="badge badge-navy">Lintas Hari</span>':''}</td>
        <td>${j.jamMasukSabtu ? j.jamMasukSabtu+' - '+j.jamPulangSabtu : (j.kerjaSabtu?'sama seperti biasa':'libur')}</td>
        <td>${j.bisaRoster?'Ya':'-'}</td>
        <td><button class="btn btn-outline btn-sm" data-edit-jadwal="${j.kode}">Edit</button>
        ${j.kode!=='STAFF' ? `<button class="btn btn-danger btn-sm" data-del-jadwal="${j.kode}">Hapus</button>` : ''}</td>
      </tr>`).join('')}</tbody>
    </table></div>
  </div>` : ''}

  ${tab === 'cuti' ? `
  <div class="panel">
    <div class="panel-head"><h3>Master Jenis Cuti</h3></div>
    <div class="panel-body">
      <form id="leaveTypeForm" class="toolbar" style="margin-bottom:14px;">
        <input type="text" id="newLeaveType" placeholder="Nama jenis cuti baru" required>
        <button class="btn btn-primary btn-sm" type="submit">Tambah</button>
      </form>
      <div class="table-wrap"><table class="datatable">
        <thead><tr><th>Jenis Cuti</th><th>Aksi</th></tr></thead>
        <tbody>${leaveTypes.map(lt => `<tr><td>${escapeHtml(lt.nama)}</td><td><button class="btn btn-danger btn-sm" data-del-leavetype="${lt.id}">Hapus</button></td></tr>`).join('')}</tbody>
      </table></div>
    </div>
  </div>` : ''}

  ${tab === 'users' ? `
  <div class="panel" style="margin-bottom:16px;">
    <div class="panel-head"><h3>Tambah Akun HRD Baru</h3></div>
    <div class="panel-body">
      <form id="hrdUserForm">
        <div class="form-row-2">
          <div class="field"><label>Email</label><input type="email" id="newHrdEmail" required></div>
          <div class="field"><label>Password</label><input type="text" id="newHrdPassword" required></div>
        </div>
        <div class="field"><label>Kaitkan dengan Karyawan (opsional)</label>
          <select id="newHrdEmployee"><option value="">- Tidak dikaitkan -</option>${employees.map(e=>`<option value="${e.id}">${escapeHtml(e.nama)}</option>`).join('')}</select>
        </div>
        <button class="btn btn-primary" type="submit">Tambah Akun HRD</button>
      </form>
    </div>
  </div>
  <div class="panel">
    <div class="panel-head"><h3>Daftar Akun Pengguna</h3></div>
    <div class="table-wrap"><table class="datatable">
      <thead><tr><th>Email</th><th>Role</th><th>Status</th><th>Aksi</th></tr></thead>
      <tbody>${users.map(u => `<tr>
        <td>${escapeHtml(u.email)}</td><td>${u.role}</td>
        <td>${u.active!==false ? '<span class="badge badge-success">Aktif</span>' : '<span class="badge badge-danger">Nonaktif</span>'}</td>
        <td>${u.active!==false
          ? `<button class="btn btn-danger btn-sm" data-user-deactivate="${u.id}">Nonaktifkan</button>`
          : `<button class="btn btn-success btn-sm" data-user-activate="${u.id}">Aktifkan</button>`}</td>
      </tr>`).join('')}</tbody>
    </table></div>
  </div>` : ''}
  `;
}
function bindSettingsEvents(){
  document.querySelectorAll('[data-settab]').forEach(b => b.addEventListener('click', () => goTo('settings', {tab: b.getAttribute('data-settab')})));

  const form = document.getElementById('settingsForm');
  if(form) form.addEventListener('submit', e => {
    e.preventDefault();
    try{
      updateOfficeSettings({
        companyName: document.getElementById('sNama').value,
        lat: parseFloat(document.getElementById('sLat').value),
        lng: parseFloat(document.getElementById('sLng').value),
        radius: parseInt(document.getElementById('sRadius').value, 10),
        batasKeterlambatan: parseInt(document.getElementById('sBatas').value || 0, 10),
        jamMasuk: document.getElementById('sJamMasuk').value,
        jamPulang: document.getElementById('sJamPulang').value,
        bpjsTkKaryawanPersen: parseFloat(document.getElementById('sBpjsKaryawan').value || 0),
        bpjsTkPerusahaanPersen: parseFloat(document.getElementById('sBpjsPerusahaan').value || 0),
        bpjsKesehatanKaryawanPersen: parseFloat(document.getElementById('sBpjsKesKaryawan').value || 0),
        bpjsKesehatanPerusahaanPersen: parseFloat(document.getElementById('sBpjsKesPerusahaan').value || 0),
        potonganTelatPerHari: parseInt(document.getElementById('sPotonganTelat').value || 0, 10),
        tanggalMulaiAbsensi: document.getElementById('sTanggalMulai').value
      });
      toast('Pengaturan kantor berhasil disimpan.', 'success');
      render();
    }catch(err){ toast(err.message, 'error'); }
  });

  const jadwalForm = document.getElementById('jadwalForm');
  if(jadwalForm) jadwalForm.addEventListener('submit', e => {
    e.preventDefault();
    const editKode = ROUTE.params && ROUTE.params.editJadwal;
    try{
      saveJadwalKerja({
        kode: document.getElementById('jKode').value.trim().toUpperCase(),
        nama: document.getElementById('jNama').value,
        jamMasuk: document.getElementById('jJamMasuk').value,
        jamPulang: document.getElementById('jJamPulang').value,
        jamMasukSabtu: document.getElementById('jJamMasukSabtu').value,
        jamPulangSabtu: document.getElementById('jJamPulangSabtu').value,
        kerjaSabtu: document.getElementById('jKerjaSabtu').checked,
        kerjaMinggu: false,
        overnight: document.getElementById('jOvernight').checked,
        bisaRoster: document.getElementById('jBisaRoster').checked
      }, editKode);
      toast('Jadwal kerja berhasil disimpan.', 'success');
      goTo('settings', {tab:'jadwal'});
    }catch(err){ toast(err.message, 'error'); }
  });
  document.querySelectorAll('[data-edit-jadwal]').forEach(b => b.addEventListener('click', () => goTo('settings', {tab:'jadwal', editJadwal: b.getAttribute('data-edit-jadwal')})));
  document.querySelectorAll('[data-del-jadwal]').forEach(b => b.addEventListener('click', () => {
    if(!confirm('Hapus jadwal ini? Karyawan yang masih pakai jadwal ini akan otomatis dianggap STAFF.')) return;
    try{ deleteJadwalKerja(b.getAttribute('data-del-jadwal')); toast('Jadwal dihapus.', 'success'); goTo('settings', {tab:'jadwal'}); }
    catch(err){ toast(err.message, 'error'); }
  }));
  const jadwalCancelBtn = document.getElementById('jadwalCancelBtn');
  if(jadwalCancelBtn) jadwalCancelBtn.addEventListener('click', () => goTo('settings', {tab:'jadwal'}));

  const ltForm = document.getElementById('leaveTypeForm');
  if(ltForm) ltForm.addEventListener('submit', e => {
    e.preventDefault();
    try{
      addLeaveType(document.getElementById('newLeaveType').value);
      toast('Jenis cuti ditambahkan.', 'success');
      goTo('settings', {tab:'cuti'});
    }catch(err){ toast(err.message, 'error'); }
  });
  document.querySelectorAll('[data-del-leavetype]').forEach(b => b.addEventListener('click', () => {
    try{ removeLeaveType(b.getAttribute('data-del-leavetype')); toast('Jenis cuti dihapus.', 'success'); goTo('settings', {tab:'cuti'}); }
    catch(err){ toast(err.message, 'error'); }
  }));

  const hrdForm = document.getElementById('hrdUserForm');
  if(hrdForm) hrdForm.addEventListener('submit', e => {
    e.preventDefault();
    try{
      createHRDUser(document.getElementById('newHrdEmail').value, document.getElementById('newHrdPassword').value, document.getElementById('newHrdEmployee').value);
      toast('Akun HRD baru berhasil dibuat.', 'success');
      goTo('settings', {tab:'users'});
    }catch(err){ toast(err.message, 'error'); }
  });
  document.querySelectorAll('[data-user-deactivate]').forEach(b => b.addEventListener('click', () => {
    try{ setUserActive(b.getAttribute('data-user-deactivate'), false); toast('Akun dinonaktifkan.', 'success'); goTo('settings', {tab:'users'}); }
    catch(err){ toast(err.message, 'error'); }
  }));
  document.querySelectorAll('[data-user-activate]').forEach(b => b.addEventListener('click', () => {
    try{ setUserActive(b.getAttribute('data-user-activate'), true); toast('Akun diaktifkan.', 'success'); goTo('settings', {tab:'users'}); }
    catch(err){ toast(err.message, 'error'); }
  }));
}

/* ---- Audit log page ---- */
function renderAuditPage(){
  const logs = DB.auditLogs();
  return `
  <div class="panel">
    <div class="panel-head"><h3>Audit Log (${logs.length})</h3><button class="btn btn-outline btn-sm" id="auditExportBtn">Export CSV</button></div>
    <div class="table-wrap"><table class="datatable">
      <thead><tr><th>Waktu</th><th>User</th><th>Role</th><th>Aktivitas</th><th>Data</th><th>Sebelum</th><th>Sesudah</th></tr></thead>
      <tbody>${logs.length ? logs.slice(0,300).map(l => `<tr>
        <td class="small">${fmtDateTime(l.waktu)}</td><td class="small">${escapeHtml(l.user)}</td><td class="small">${escapeHtml(l.role)}</td>
        <td class="small">${escapeHtml(l.aktivitas)}</td><td class="small">${escapeHtml(l.data)}</td>
        <td class="small">${escapeHtml(l.statusSebelum)}</td><td class="small">${escapeHtml(l.statusSesudah)}</td>
      </tr>`).join('') : `<tr><td colspan="7" class="empty-row">Belum ada aktivitas tercatat</td></tr>`}</tbody>
    </table></div>
  </div>
  <p class="hint">Audit log bersifat permanen dan tidak dapat dihapus oleh siapa pun melalui aplikasi ini, termasuk karyawan maupun HRD.</p>`;
}
function bindAuditEvents(){
  const btn = document.getElementById('auditExportBtn');
  if(btn) btn.addEventListener('click', () => {
    const csv = toCSV(DB.auditLogs(), [
      {label:'Waktu', value: l => fmtDateTime(l.waktu)}, {label:'User', value:'user'}, {label:'Role', value:'role'},
      {label:'Aktivitas', value:'aktivitas'}, {label:'Data', value:'data'}, {label:'Status Sebelum', value:'statusSebelum'}, {label:'Status Sesudah', value:'statusSesudah'}
    ]);
    downloadCSV('audit_log.csv', csv);
  });
}

/* ---- Calendar page ---- */
function monthEvents(year, month){
  const mm = String(month+1).padStart(2,'0');
  const prefix = year + '-' + mm;
  const events = {};
  function add(dateStr, label){
    if(!dateStr || !dateStr.startsWith(prefix)) return;
    events[dateStr] = events[dateStr] || [];
    events[dateStr].push(label);
  }
  DB.leaveRequests().filter(r=>r.status!=='DITOLAK').forEach(r => {
    let d = new Date(r.tglMulai + 'T00:00:00');
    const end = new Date(r.tglSelesai + 'T00:00:00');
    while(d <= end){ add(d.toISOString().slice(0,10), 'Cuti: ' + r.nama); d.setDate(d.getDate()+1); }
  });
  DB.permissionRequests().filter(r=>r.status!=='DITOLAK').forEach(r => add(r.tanggal, 'Izin: ' + r.nama));
  DB.overtimeRequests().filter(r=>r.status!=='DITOLAK').forEach(r => add(r.tanggal, 'Lembur: ' + r.nama));
  return events;
}
function renderCalendarPage(){
  const year = UI.calYear, month = UI.calMonth;
  const events = monthEvents(year, month);
  const first = new Date(year, month, 1);
  const startWeekday = first.getDay();
  const daysInMonth = new Date(year, month+1, 0).getDate();
  const bulanNama = ['Januari','Februari','Maret','April','Mei','Juni','Juli','Agustus','September','Oktober','November','Desember'];

  let cells = '';
  for(let i=0;i<startWeekday;i++) cells += `<div class="cal-cell empty"></div>`;
  for(let d=1; d<=daysInMonth; d++){
    const dateStr = year + '-' + String(month+1).padStart(2,'0') + '-' + String(d).padStart(2,'0');
    const isToday = dateStr === todayISO();
    const isSel = dateStr === UI.selectedCalDate;
    const evs = events[dateStr] || [];
    cells += `<div class="cal-cell ${isToday?'today':''} ${isSel?'sel':''}" data-caldate="${dateStr}">
      <div class="d">${d}</div>
      ${evs.slice(0,3).map(()=>'<span class="cal-dot"></span>').join('')}
    </div>`;
  }
  const selEvents = UI.selectedCalDate ? (events[UI.selectedCalDate] || []) : [];

  return `
  <div class="panel">
    <div class="panel-head">
      <h3>${bulanNama[month]} ${year}</h3>
      <div class="toolbar">
        <button class="btn btn-outline btn-sm" id="calPrevBtn">&larr;</button>
        <button class="btn btn-outline btn-sm" id="calNextBtn">&rarr;</button>
      </div>
    </div>
    <div class="panel-body">
      <div class="cal-grid">${cells}</div>
    </div>
  </div>
  <div class="section-title">${UI.selectedCalDate ? 'Pengajuan pada ' + fmtDate(UI.selectedCalDate) : 'Pilih tanggal untuk melihat detail'}</div>
  <div class="panel"><div class="panel-body">
    ${selEvents.length ? `<ul style="margin:0;padding-left:18px;">${selEvents.map(e=>`<li>${escapeHtml(e)}</li>`).join('')}</ul>` : `<div class="muted small">Tidak ada pengajuan pada tanggal ini.</div>`}
  </div></div>`;
}
function bindCalendarEvents(){
  document.querySelectorAll('[data-caldate]').forEach(c => c.addEventListener('click', () => { UI.selectedCalDate = c.getAttribute('data-caldate'); render(); }));
  const prev = document.getElementById('calPrevBtn');
  const next = document.getElementById('calNextBtn');
  if(prev) prev.addEventListener('click', () => { UI.calMonth--; if(UI.calMonth<0){UI.calMonth=11;UI.calYear--;} render(); });
  if(next) next.addEventListener('click', () => { UI.calMonth++; if(UI.calMonth>11){UI.calMonth=0;UI.calYear++;} render(); });
}

/* Wire the dashboard's inline approve/reject buttons + contracts export
   (registered here since renderPage dispatch above doesn't have a case
   for these two - dashboard needs approval bindings, contracts needs export binding) */
const _origBindPageEvents = bindPageEvents;
bindPageEvents = function(u){
  _origBindPageEvents(u);
  if(u.role === 'HRD' && ROUTE.page === 'dashboard') bindApprovalActionEvents(() => render());
  if(u.role === 'HRD' && !UI.alphaChecked){
    UI.alphaChecked = true;
    setTimeout(() => {
      detectAndMarkAlpha((jumlah) => {
        if(jumlah > 0){
          toast(jumlah + ' catatan Alpha baru terdeteksi dari hari kerja yang terlewat.', 'error');
          render();
        }
      });
    }, 50);
  }
  if(u.role === 'HRD' && ROUTE.page === 'contracts') bindContractsEvents();
};

/* ---------------------------------------------------------------------
   19. BOOTSTRAP
--------------------------------------------------------------------- */
async function boot(){
  const appEl = document.getElementById('app');
  appEl.innerHTML = '<div style="padding:60px 20px;text-align:center;color:#8A8272;">Memuat data dari server...</div>';
  try{
    await loadAllFromServer();
  }catch(e){
    appEl.innerHTML = '<div style="padding:60px 20px;text-align:center;color:#B33F32;">Gagal memuat data dari server.<br>Cek koneksi internet kamu, atau pastikan API_URL di app.js sudah diganti dengan URL Web App Apps Script yang benar.</div>';
    return;
  }
  seedIfEmpty();
  ensureMasterDataSeeded();
  render();
}
boot();

</script>
</body>
</html>
