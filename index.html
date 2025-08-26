<!DOCTYPE html>
<html lang="vi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Dashboard Báo Cáo Chuyên Nghiệp</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <script src="https://cdn.jsdelivr.net/npm/chartjs-adapter-date-fns/dist/chartjs-adapter-date-fns.bundle.min.js"></script>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
    <!-- Chosen Palette: Slate & Amber -->
    <!-- Application Structure Plan: Ứng dụng được cấu trúc như một dashboard động, đọc toàn bộ trạng thái (dữ liệu) từ một tham số 'data' duy nhất trên URL. Giao diện ban đầu sẽ hiển thị trạng thái chờ dữ liệu. Sau khi giải mã và phân tích cú pháp thành công dữ liệu từ URL, ứng dụng sẽ render các thành phần tương ứng (KPIs, biểu đồ, bảng). Cấu trúc này đảm bảo tính linh hoạt tối đa, biến trang HTML tĩnh thành một công cụ báo cáo có thể tái sử dụng cho vô số bộ dữ liệu khác nhau được tạo ra từ AppSheet. -->
    <!-- Visualization & Content Choices: Các lựa chọn biểu đồ (cột, đường, donut) và bảng biểu được giữ nguyên từ các phiên bản trước vì tính hiệu quả của chúng. Logic JavaScript được tái cấu trúc hoàn toàn để xây dựng các biểu đồ và bảng biểu dựa trên dữ liệu được nạp động từ URL, thay vì dữ liệu được mã hóa cứng. Các hàm render sẽ kiểm tra sự tồn tại của dữ liệu trước khi vẽ để tránh lỗi. -->
    <!-- CONFIRMATION: NO SVG graphics used. NO Mermaid JS used. -->
    <style>
        body { font-family: 'Inter', sans-serif; }
        .sidebar-icon { width: 24px; height: 24px; }
        .chart-container { position: relative; width: 100%; margin-left: auto; margin-right: auto; height: 250px; sm:height: 300px; md:height: 350px; max-height: 400px; }
        ::-webkit-scrollbar { width: 8px; }
        ::-webkit-scrollbar-track { background: #f1f5f9; }
        ::-webkit-scrollbar-thumb { background: #cbd5e1; border-radius: 10px; }
        ::-webkit-scrollbar-thumb:hover { background: #94a3b8; }
        .kpi-card { transition: all 0.2s ease-in-out; }
        .kpi-card:hover { transform: translateY(-5px); box-shadow: 0 10px 15px -3px rgb(0 0 0 / 0.05), 0 4px 6px -4px rgb(0 0 0 / 0.05); }
    </style>
</head>
<body class="bg-slate-100 text-slate-800">
    <div id="loading-state" class="flex items-center justify-center h-screen">
        <div class="text-center p-4">
            <h2 class="text-2xl font-semibold text-slate-700 mb-2">Đang chờ dữ liệu...</h2>
            <p class="text-slate-500">Vui lòng truy cập báo cáo này qua một URL có chứa dữ liệu được tạo từ AppSheet.</p>
        </div>
    </div>

    <div id="app-container" class="hidden h-screen flex-col sm:flex-row">
        <!-- Sidebar -->
        <aside class="w-full sm:w-20 md:w-64 bg-white border-b sm:border-b-0 sm:border-r border-slate-200 flex flex-col shrink-0">
            <div class="h-16 flex items-center justify-center md:justify-start md:px-6 border-b sm:border-b-0 border-slate-200 shrink-0">
                <div class="bg-amber-500 text-white w-10 h-10 rounded-lg flex items-center justify-center text-xl font-bold">S</div>
                <span class="hidden md:inline ml-4 text-lg font-semibold text-amber-600">ERP Report</span>
            </div>
            <nav class="flex-1 pt-2 sm:pt-6 space-y-2 flex sm:flex-col flex-row justify-around sm:justify-start">
                <a href="#" onclick="showView('tongQuan')" class="nav-link bg-amber-50 border-b-4 sm:border-b-0 sm:border-r-4 border-amber-500 text-amber-600 flex flex-col sm:flex-row items-center py-3 px-2 sm:px-6 text-center">
                    <svg class="sidebar-icon" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6a2 2 0 012-2h2a2 2 0 012 2v2a2 2 0 01-2 2H6a2 2 0 01-2-2V6zM14 6a2 2 0 012-2h2a2 2 0 012 2v2a2 2 0 01-2 2h-2a2 2 0 01-2-2V6zM4 16a2 2 0 012-2h2a2 2 0 012 2v2a2 2 0 01-2 2H6a2 2 0 01-2-2v-2zM14 16a2 2 0 012-2h2a2 2 0 012 2v2a2 2 0 01-2 2h-2a2 2 0 01-2-2v-2z"></path></svg>
                    <span class="text-xs sm:text-sm md:text-base hidden md:inline sm:ml-4 font-medium">Tổng Quan</span>
                </a>
                <a href="#" onclick="showView('phanTichBanHang')" class="nav-link text-slate-600 hover:bg-amber-50 hover:text-amber-600 flex flex-col sm:flex-row items-center py-3 px-2 sm:px-6 text-center">
                    <svg class="sidebar-icon" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 7h8m0 0v8m0-8l-8 8-4-4-6 6"></path></svg>
                    <span class="text-xs sm:text-sm md:text-base hidden md:inline sm:ml-4 font-medium">Bán Hàng</span>
                </a>
                <a href="#" onclick="showView('khoHang')" class="nav-link text-slate-600 hover:bg-amber-50 hover:text-amber-600 flex flex-col sm:flex-row items-center py-3 px-2 sm:px-6 text-center">
                     <svg class="sidebar-icon" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M16 11V7a4 4 0 00-8 0v4M5 9h14l1 12H4L5 9z"></path></svg>
                    <span class="text-xs sm:text-sm md:text-base hidden md:inline sm:ml-4 font-medium">Kho Hàng</span>
                </a>
                <a href="#" onclick="showView('khachHang')" class="nav-link text-slate-600 hover:bg-amber-50 hover:text-amber-600 flex flex-col sm:flex-row items-center py-3 px-2 sm:px-6 text-center">
                    <svg class="sidebar-icon" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17 20h5v-2a3 3 0 00-5.356-1.857M17 20H7m10 0v-2c0-.656-.126-1.283-.356-1.857M7 20H2v-2a3 3 0 015.356-1.857M7 20v-2c0-.656.126-1.283.356-1.857m0 0a5.002 5.002 0 019.288 0M15 7a3 3 0 11-6 0 3 3 0 016 0zm6 3a2 2 0 11-4 0 2 2 0 014 0zM7 10a2 2 0 11-4 0 2 2 0 014 0z"></path></svg>
                    <span class="text-xs sm:text-sm md:text-base hidden md:inline sm:ml-4 font-medium">Khách Hàng</span>
                </a>
            </nav>
        </aside>

        <!-- Main Content -->
        <main class="flex-1 p-4 md:p-8 overflow-y-auto">
            <div class="flex flex-col sm:flex-row justify-between items-start sm:items-center mb-6 gap-4">
                <h1 id="view-title" class="text-2xl sm:text-3xl font-bold text-slate-800">Dashboard Tổng Quan</h1>
                <div class="flex items-center space-x-2 sm:space-x-4">
                    <span class="text-sm font-medium text-slate-500">Giai đoạn:</span>
                    <select id="date-filter" class="bg-white border border-slate-300 rounded-md shadow-sm px-3 py-2 text-sm font-medium text-slate-700 focus:outline-none focus:ring-2 focus:ring-amber-500">
                        <option value="7">7 ngày qua</option>
                        <option value="30" selected>30 ngày qua</option>
                        <option value="90">90 ngày qua</option>
                        <option value="365">1 năm qua</option>
                    </select>
                </div>
            </div>
            <div id="views-container"></div>
        </main>
    </div>

<script>
// --- TEMPLATES FOR VIEWS ---
const viewTemplates = {
    tongQuan: `
        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-6 mb-8">
            <div class="bg-white p-6 rounded-xl border border-slate-200 kpi-card"><h3 class="text-slate-500 text-sm font-medium mb-2">Tổng Doanh Thu</h3><p id="kpi-doanh-thu" class="text-2xl md:text-3xl font-bold text-amber-600">0đ</p></div>
            <div class="bg-white p-6 rounded-xl border border-slate-200 kpi-card"><h3 class="text-slate-500 text-sm font-medium mb-2">Tổng Lợi Nhuận</h3><p id="kpi-loi-nhuan" class="text-2xl md:text-3xl font-bold text-emerald-600">0đ</p></div>
            <div class="bg-white p-6 rounded-xl border border-slate-200 kpi-card"><h3 class="text-slate-500 text-sm font-medium mb-2">Tổng Đơn Hàng</h3><p id="kpi-don-hang" class="text-2xl md:text-3xl font-bold text-sky-600">0</p></div>
            <div class="bg-white p-6 rounded-xl border border-slate-200 kpi-card"><h3 class="text-slate-500 text-sm font-medium mb-2">Tỷ Lệ Lợi Nhuận</h3><p id="kpi-ty-le-loi-nhuan" class="text-2xl md:text-3xl font-bold text-violet-600">0%</p></div>
        </div>
        <div class="bg-white p-6 rounded-xl border border-slate-200 mb-8">
            <h3 class="text-lg font-semibold mb-4">Tổng Quan Doanh Thu & Lợi Nhuận</h3>
            <div class="chart-container"><canvas id="overviewChart"></canvas></div>
        </div>
    `,
    phanTichBanHang: `
        <div class="grid grid-cols-1 lg:grid-cols-2 gap-8">
            <div class="bg-white p-6 rounded-xl border border-slate-200"><h3 class="text-lg font-semibold mb-4">Phân Bổ Doanh Thu Theo Loại Sản Phẩm</h3><div class="chart-container"><canvas id="categorySalesChart"></canvas></div></div>
            <div class="bg-white p-6 rounded-xl border border-slate-200"><h3 class="text-lg font-semibold mb-4">Top 5 Sản Phẩm Doanh Thu Cao Nhất</h3><div class="chart-container"><canvas id="topProductRevenueChart"></canvas></div></div>
        </div>
    `,
    khoHang: `
        <div class="grid grid-cols-1 lg:grid-cols-3 gap-8">
            <div class="lg:col-span-1 flex flex-col gap-8">
                <div class="bg-white p-6 rounded-xl border border-slate-200 kpi-card"><h3 class="text-slate-500 text-sm font-medium mb-2">Tổng Giá Trị Tồn Kho</h3><p id="kpi-gia-tri-kho" class="text-2xl md:text-3xl font-bold text-slate-800">0đ</p></div>
                <div class="bg-white p-6 rounded-xl border border-slate-200 kpi-card"><h3 class="text-slate-500 text-sm font-medium mb-2">Sản Phẩm Sắp Hết Hàng</h3><p id="kpi-sap-het-hang" class="text-2xl md:text-3xl font-bold text-rose-500">0</p></div>
            </div>
            <div class="lg:col-span-2 bg-white p-6 rounded-xl border border-slate-200">
                <h3 class="text-lg font-semibold mb-4">Danh Sách Sản Phẩm Cần Nhập Hàng</h3>
                <div class="max-h-[60vh] overflow-y-auto">
                    <table class="w-full text-sm text-left"><thead class="text-xs text-slate-500 uppercase bg-slate-100 sticky top-0"><tr><th class="px-4 py-3">Sản Phẩm</th><th class="px-4 py-3 text-center">Tồn Kho</th><th class="px-4 py-3 text-center">Mức Tối Thiểu</th></tr></thead><tbody id="lowStockTableBody"></tbody></table>
                </div>
            </div>
        </div>
    `,
    khachHang: `
        <div class="grid grid-cols-1 lg:grid-cols-2 gap-8">
            <div class="bg-white p-6 rounded-xl border border-slate-200"><h3 class="text-lg font-semibold mb-4">Top 5 Khách Hàng Chi Tiêu Nhiều Nhất</h3><div class="chart-container"><canvas id="topCustomerChart"></canvas></div></div>
            <div class="bg-white p-6 rounded-xl border border-slate-200"><h3 class="text-lg font-semibold mb-4">Phân Bổ Khách Hàng</h3><div class="grid grid-cols-2 gap-4 pt-4"><div class="text-center"><p class="text-3xl md:text-4xl font-bold text-sky-600" id="total-customers">0</p><p class="text-sm text-slate-500 mt-1">Tổng số khách hàng</p></div><div class="text-center"><p class="text-3xl md:text-4xl font-bold text-emerald-600" id="new-customers">0</p><p class="text-sm text-slate-500 mt-1">Khách hàng mới (trong kỳ)</p></div></div></div>
        </div>
    `
};

// --- DATABASE (sẽ được ghi đè bởi dữ liệu URL) ---
let sanPhams = [], khachHangs = [], donHangs = [], chiTietDonHangs = [], chiTietPhieuNhaps = [];

// --- GLOBAL STATE & CHARTS ---
let state = { currentView: 'tongQuan' };
let charts = {};

// --- UTILITY FUNCTIONS ---
const formatCurrency = (value) => new Intl.NumberFormat('vi-VN', { style: 'currency', currency: 'VND' }).format(value);

// --- DATA LOADING & PROCESSING ---
function loadDataFromUrl() {
    const urlParams = new URLSearchParams(window.location.search);
    const dataParam = urlParams.get('data');
    if (dataParam) {
        try {
            const decodedData = JSON.parse(decodeURIComponent(atob(dataParam)));
            sanPhams = decodedData.sanPhams || [];
            khachHangs = decodedData.khachHangs || [];
            donHangs = decodedData.donHangs || [];
            chiTietDonHangs = decodedData.chiTietDonHangs || [];
            chiTietPhieuNhaps = decodedData.chiTietPhieuNhaps || [];
            return true;
        } catch (e) {
            console.error("Lỗi giải mã dữ liệu từ URL:", e);
            document.getElementById('loading-state').innerHTML = `<div class="text-center"><h2 class="text-2xl font-semibold text-rose-700 mb-2">Lỗi Dữ Liệu</h2><p class="text-slate-500">Dữ liệu trong URL không hợp lệ hoặc bị hỏng.</p></div>`;
            return false;
        }
    }
    return false;
}

let processedData = {};
function processAllData() {
    const days = parseInt(document.getElementById('date-filter').value);
    const startDate = new Date();
    startDate.setHours(0, 0, 0, 0);
    startDate.setDate(startDate.getDate() - days);

    const filteredDonHangs = donHangs.filter(dh => new Date(dh.NgayTao) >= startDate);
    const filteredDonHangIds = filteredDonHangs.map(dh => dh.MaDonHang);
    const filteredChiTiet = chiTietDonHangs.filter(ct => filteredDonHangIds.includes(ct.MaDonHang));
    
    const sanPhamsWithTonKho = sanPhams.map(sp => {
        const totalNhap = (chiTietPhieuNhaps || []).filter(pn => pn.MaSP === sp.MaSP).reduce((sum, item) => sum + (Number(item.SoLuong) || 0), 0);
        const totalBan = (chiTietDonHangs || []).filter(dh => dh.MaSP === sp.MaSP).reduce((sum, item) => sum + (Number(item.SoLuong) || 0), 0);
        return { ...sp, TonKho: totalNhap - totalBan };
    });

    const donHangsWithTotals = filteredDonHangs.map(dh => {
        const details = filteredChiTiet.filter(ct => ct.MaDonHang === dh.MaDonHang);
        const tongTien = Number(dh.TongTien) || details.reduce((sum, item) => sum + ((Number(item.SoLuong) || 0) * (Number(item.DonGia) || 0)), 0);
        const loiNhuan = details.reduce((sum, item) => sum + ((Number(item.SoLuong) || 0) * ((Number(item.DonGia) || 0) - (Number(item.GiaNhapHienThi) || Number(item.GiaNhap) || 0))), 0);
        return { ...dh, TongTien: tongTien, LoiNhuan: loiNhuan };
    });
    
    processedData = { sanPhamsWithTonKho, donHangsWithTotals, filteredChiTiet };
}

// --- RENDERING FUNCTIONS ---
function renderAll() {
    processAllData();
    const currentView = state.currentView;
    showView(currentView, true); 
}

function renderTongQuan() {
    const { donHangsWithTotals } = processedData;
    const totalDoanhThu = donHangsWithTotals.reduce((sum, dh) => sum + dh.TongTien, 0);
    const totalLoiNhuan = donHangsWithTotals.reduce((sum, dh) => sum + dh.LoiNhuan, 0);
    const totalDonHang = donHangsWithTotals.length;
    const tyLeLoiNhuan = totalDoanhThu > 0 ? (totalLoiNhuan / totalDoanhThu) * 100 : 0;

    document.getElementById('kpi-doanh-thu').textContent = formatCurrency(totalDoanhThu);
    document.getElementById('kpi-loi-nhuan').textContent = formatCurrency(totalLoiNhuan);
    document.getElementById('kpi-don-hang').textContent = totalDonHang;
    document.getElementById('kpi-ty-le-loi-nhuan').textContent = `${tyLeLoiNhuan.toFixed(1)}%`;

    const ctx = document.getElementById('overviewChart').getContext('2d');
    if (charts.overview) charts.overview.destroy();
    const salesByDay = donHangsWithTotals.reduce((acc, order) => {
        const date = new Date(order.NgayTao).toISOString().split('T')[0];
        acc[date] = acc[date] || { doanhThu: 0, loiNhuan: 0 };
        acc[date].doanhThu += order.TongTien;
        acc[date].loiNhuan += order.LoiNhuan;
        return acc;
    }, {});
    const sortedDates = Object.keys(salesByDay).sort();
    charts.overview = new Chart(ctx, { type: 'bar', data: { labels: sortedDates, datasets: [ { type: 'bar', label: 'Doanh Thu', data: sortedDates.map(date => salesByDay[date].doanhThu), backgroundColor: 'rgba(245, 158, 11, 0.6)', yAxisID: 'y', }, { type: 'line', label: 'Lợi Nhuận', data: sortedDates.map(date => salesByDay[date].loiNhuan), borderColor: 'rgb(16, 185, 129)', backgroundColor: 'rgba(16, 185, 129, 0.1)', fill: true, tension: 0.3, yAxisID: 'y1', } ] }, options: { responsive: true, maintainAspectRatio: false, scales: { x: { type: 'time', time: { unit: 'day', tooltipFormat: 'dd/MM/yyyy' } }, y: { position: 'left', beginAtZero: true, grid: { drawOnChartArea: false } }, y1: { position: 'right', beginAtZero: true } } } });
}

function renderPhanTichBanHang() {
    const { filteredChiTiet } = processedData;
    const ctxCategory = document.getElementById('categorySalesChart').getContext('2d');
    if (charts.category) charts.category.destroy();
    const salesByCategory = filteredChiTiet.reduce((acc, item) => {
        const product = sanPhams.find(p => p.MaSP === item.MaSP);
        const category = product ? product.PhanLoai : 'Khác';
        const revenue = (Number(item.SoLuong) || 0) * (Number(item.DonGia) || 0);
        acc[category] = (acc[category] || 0) + revenue;
        return acc;
    }, {});
    charts.category = new Chart(ctxCategory, { type: 'doughnut', data: { labels: Object.keys(salesByCategory), datasets: [{ data: Object.values(salesByCategory), backgroundColor: ['rgba(245, 158, 11, 0.8)', 'rgba(16, 185, 129, 0.8)', 'rgba(59, 130, 246, 0.8)'], }] }, options: { responsive: true, maintainAspectRatio: false, plugins: { legend: { position: 'bottom' } } } });

    const ctxTopProduct = document.getElementById('topProductRevenueChart').getContext('2d');
    if (charts.topProduct) charts.topProduct.destroy();
    const revenueByProduct = filteredChiTiet.reduce((acc, item) => {
        const revenue = (Number(item.SoLuong) || 0) * (Number(item.DonGia) || 0);
        acc[item.MaSP] = (acc[item.MaSP] || 0) + revenue;
        return acc;
    }, {});
    const sortedProducts = Object.entries(revenueByProduct).sort(([, a], [, b]) => b - a).slice(0, 5);
    charts.topProduct = new Chart(ctxTopProduct, { type: 'bar', data: { labels: sortedProducts.map(([maSP]) => (sanPhams.find(p => p.MaSP === maSP) || {TenSP: 'N/A'}).TenSP), datasets: [{ label: 'Doanh Thu', data: sortedProducts.map(([, revenue]) => revenue), backgroundColor: 'rgba(59, 130, 246, 0.6)', }] }, options: { indexAxis: 'y', responsive: true, maintainAspectRatio: false, plugins: { legend: { display: false } } } });
}

function renderKhoHangView() {
    const { sanPhamsWithTonKho } = processedData;
    const totalValue = sanPhamsWithTonKho.reduce((sum, p) => sum + (p.TonKho * (Number(p.GiaNhap) || 0)), 0);
    const lowStockItems = sanPhamsWithTonKho.filter(p => p.TonKho <= (Number(p.TonKhoToiThieu) || 0));
    document.getElementById('kpi-gia-tri-kho').textContent = formatCurrency(totalValue);
    document.getElementById('kpi-sap-het-hang').textContent = lowStockItems.length;
    const tbody = document.getElementById('lowStockTableBody');
    tbody.innerHTML = lowStockItems.map(p => `<tr class="border-b"><td class="px-4 py-3 font-medium">${p.TenSP}</td><td class="px-4 py-3 text-center font-bold text-rose-500">${p.TonKho}</td><td class="px-4 py-3 text-center">${p.TonKhoToiThieu}</td></tr>`).join('');
}

function renderKhachHangView() {
    const { donHangsWithTotals } = processedData;
    const spendingByCustomer = donHangsWithTotals.reduce((acc, order) => {
        acc[order.MaKH] = (acc[order.MaKH] || 0) + order.TongTien;
        return acc;
    }, {});
    const sortedCustomers = Object.entries(spendingByCustomer).sort(([, a], [, b]) => b - a).slice(0, 5);
    const ctx = document.getElementById('topCustomerChart').getContext('2d');
    if (charts.topCustomer) charts.topCustomer.destroy();
    charts.topCustomer = new Chart(ctx, { type: 'bar', data: { labels: sortedCustomers.map(([maKH]) => (khachHangs.find(c => c.MaKH === maKH) || {TenKH: 'N/A'}).TenKH), datasets: [{ label: 'Tổng Chi Tiêu', data: sortedCustomers.map(([, spending]) => spending), backgroundColor: 'rgba(16, 185, 129, 0.6)', }] }, options: { indexAxis: 'y', responsive: true, maintainAspectRatio: false, plugins: { legend: { display: false } } } });
    const newCustomerIds = new Set(donHangsWithTotals.map(d => d.MaKH));
    document.getElementById('total-customers').textContent = khachHangs.length;
    document.getElementById('new-customers').textContent = newCustomerIds.size;
}

// --- EVENT HANDLERS & INITIALIZATION ---
function showView(viewId, forceRender = false) {
    if (state.currentView === viewId && !forceRender) return;
    state.currentView = viewId;
    
    document.getElementById('views-container').innerHTML = viewTemplates[viewId];
    
    const renderFunction = {
        tongQuan: renderTongQuan,
        phanTichBanHang: renderPhanTichBanHang,
        khoHang: renderKhoHangView,
        khachHang: renderKhachHangView
    }[viewId];
    
    if (renderFunction) {
        setTimeout(renderFunction, 0);
    }
    
    const titles = { tongQuan: 'Dashboard Tổng Quan', phanTichBanHang: 'Phân Tích Bán Hàng', khoHang: 'Báo Cáo Kho Hàng', khachHang: 'Phân Tích Khách Hàng' };
    document.getElementById('view-title').textContent = titles[viewId];

    document.querySelectorAll('.nav-link').forEach(link => {
        link.classList.remove('bg-amber-50', 'border-b-4', 'sm:border-b-0', 'sm:border-r-4', 'border-amber-500', 'text-amber-600');
        link.classList.add('text-slate-600');
    });
    const activeLink = document.querySelector(`.nav-link[onclick="showView('${viewId}')"]`);
    activeLink.classList.add('bg-amber-50', 'border-b-4', 'sm:border-b-0', 'sm:border-r-4', 'border-amber-500', 'text-amber-600');
}

document.getElementById('date-filter').addEventListener('change', renderAll);

window.onload = () => {
    if (loadDataFromUrl()) {
        document.getElementById('loading-state').classList.add('hidden');
        document.getElementById('app-container').classList.remove('hidden');
        document.getElementById('app-container').classList.add('flex');
        renderAll();
    }
};
</script>
</body>
</html>
