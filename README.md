<!doctype html>
<div style="margin-top:8px"><strong>Họ tên:</strong> ${escapeHtml(data.fullname)}</div>
<div><strong>Ngày sinh:</strong> ${escapeHtml(data.dob)}</div>
<div><strong>Giới tính:</strong> ${escapeHtml(data.gender || '—')}</div>
<div><strong>Email:</strong> ${escapeHtml(data.email)}</div>
<div><strong>SĐT:</strong> ${escapeHtml(data.phone)}</div>
<div><strong>Địa chỉ:</strong> ${escapeHtml(data.address || '—')}</div>
<div><strong>Sở thích:</strong> ${escapeHtml(data.interests || '—')}</div>
<div><strong>Loại thành viên:</strong> ${escapeHtml(data.memberType)}</div>
<div style="margin-top:10px"><em>Nếu thông tin đúng, nhấn 'Gửi đăng ký' để hoàn tất.</em></div>
`;
previewArea.style.display = 'block'; previewArea.setAttribute('aria-hidden','false');
result.innerHTML = '';
});


form.addEventListener('submit', (e)=>{
e.preventDefault();
result.innerHTML = '';
if(!validate()) return;


const data = getFormData();
// Save to localStorage (optional)
let saved = JSON.parse(localStorage.getItem('club_members') || '[]');
saved.push(Object.assign({submittedAt: new Date().toISOString()}, data));
localStorage.setItem('club_members', JSON.stringify(saved));


// Show success + download JSON
result.innerHTML = `<div style="padding:12px;border-radius:8px;background:#ecfdf5;border:1px solid #bbf7d0;color:#065f46">Đăng ký thành công! Thông tin đã được lưu (cục bộ trên trình duyệt).</div>`;


// Create downloadable JSON file for this submission
const blob = new Blob([JSON.stringify(data, null, 2)], {type: 'application/json'});
const url = URL.createObjectURL(blob);
const a = document.createElement('a');
a.href = url;
const safeName = (data.fullname || 'member').replace(/[^a-z0-9\-_.]/gi,'_');
a.download = safeName + '_registration.json';
a.textContent = 'Tải file JSON của bản đăng ký';
a.style.display = 'inline-block';
a.style.marginTop = '8px';
result.appendChild(a);


// Reset form (optional)
form.reset();
joinEl.value = today;
previewArea.style.display = 'none';


// revoke url after some time
setTimeout(()=> URL.revokeObjectURL(url), 60000);
});


// Small helper
function escapeHtml(s){ if(!s) return ''; return s.replaceAll('&','&amp;').replaceAll('<','&lt;').replaceAll('>','&gt;').replaceAll('"','&quot;') }


})();
</script>
</body>
</html>
