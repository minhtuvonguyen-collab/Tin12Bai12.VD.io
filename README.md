<!doctype html>
<html lang="vi">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Đơn đăng ký thành viên - CBT's ESC</title>
  <style>
    :root { --bg:#e8f5f0; --card:#ffffff; --primary:#1e8c6f; --accent:#2fb98d; --text:#0b3d2e; }
    body { font-family:Inter, system-ui; margin:0; background:var(--bg); color:var(--text); }
    .container { max-width:700px; margin:20px auto; padding:16px; }
    .header-img img { width:100%; border-radius:16px; box-shadow:0 4px 16px rgba(0,0,0,0.15); }
    h1 { text-align:center; margin:24px 0; color:var(--primary); font-size:26px; }
    form { background:var(--card); padding:20px; border-radius:16px; box-shadow:0 4px 12px rgba(0,0,0,0.08); display:flex; flex-direction:column; gap:16px; }
    label { font-weight:600; margin-bottom:4px; }
    input, select, textarea { padding:10px; border-radius:10px; border:1px solid #cddad4; font-size:15px; width:100%; }
    textarea { resize:vertical; min-height:90px; }
    button { margin-top:8px; background:var(--primary); color:#fff; border:0; padding:12px; border-radius:12px; font-size:16px; cursor:pointer; font-weight:600; }
    button:hover { background:var(--accent); }
  </style>
</head>
<body>
  <div class="container">
    <div class="header-img">
      <img src="Cover upgraded (1).JPG" alt="ESC banner" />
    </div>

    <h1>Đơn đăng kí thành viên Câu lạc bộ Tiếng Anh<br>CBT's English Speaking Club (ESC)</h1>

    <form>
      <div>
        <label>Họ tên</label>
        <input type="text" placeholder="Nguyễn Văn A" required />
      </div>

      <div>
        <label>Lớp</label>
        <input type="text" placeholder="12A1" required />
      </div>

      <div>
        <label>Số điện thoại</label>
        <input type="tel" placeholder="0901234567" required />
      </div>

      <div>
        <label>Địa chỉ email</label>
        <input type="email" placeholder="email@example.com" required />
      </div>

      <div>
        <label>Ban muốn đăng ký</label>
        <select required>
          <option value="">-- Chọn ban --</option>
          <option>Ban Nội dung</option>
          <option>Ban Hậu cần</option>
          <option>Ban Media</option>
          <option>Ban Sự kiện</option>
        </select>
      </div>

      <div>
        <label>Vì sao bạn chọn ban này?</label>
        <textarea placeholder="Viết lý do của bạn..." required></textarea>
      </div>

      <button type="submit">Gửi đăng ký</button>
    </form>
  </div>
</body>
</html>
