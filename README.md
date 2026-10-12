<!DOCTYPE html>
<html lang="vi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>H+ Studio - Quản lý Nhân sự & đối tác</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        body {
            font-family: 'Inter', sans-serif;
            background-color: #f7f6f3;
            color: #1a1a1a;
        }
        .sidebar-item.active {
            background-color: #e2e8f0;
            font-weight: 600;
        }
    </style>
</head>
<body class="flex h-screen overflow-hidden">

    <!-- Sidebar -->
    <aside class="w-64 bg-[#f0eee6] border-r border-stone-300 flex flex-col justify-between shrink-0 select-none">
        <div>
            <!-- Logo Header -->
            <div class="p-6 border-b border-stone-300">
                <div class="flex items-center space-x-2">
                    <div class="bg-black text-white font-bold p-2 px-3 text-xl tracking-wider rounded">H</div>
                    <div>
                        <h1 class="font-bold tracking-widest text-lg leading-none">STUDIO</h1>
                        <span class="text-[10px] text-stone-500 tracking-wider uppercase font-medium">VẬN HÀNH</span>
                    </div>
                </div>
            </div>

            <!-- Navigation Links -->
            <nav class="p-3 space-y-1 text-sm">
                <a href="#" class="flex items-center justify-between px-3 py-2.5 rounded-lg text-stone-700 hover:bg-stone-200 transition">
                    <span>Tổng quan</span>
                </a>
                <a href="#" class="flex items-center justify-between px-3 py-2.5 rounded-lg text-stone-700 hover:bg-stone-200 transition">
                    <span>Dự án</span>
                    <span class="text-xs bg-stone-300 px-1.5 py-0.5 rounded text-stone-600">0</span>
                </a>
                <a href="#" class="flex items-center justify-between px-3 py-2.5 rounded-lg text-stone-700 hover:bg-stone-200 transition">
                    <span>Công việc</span>
                    <span class="text-xs bg-stone-300 px-1.5 py-0.5 rounded text-stone-600">0</span>
                </a>
                <a href="#" class="flex items-center justify-between px-3 py-2.5 rounded-lg text-stone-700 hover:bg-stone-200 transition">
                    <span>Thu chi</span>
                </a>
                <a href="#" class="flex items-center justify-between px-3 py-2.5 rounded-lg text-stone-700 hover:bg-stone-200 transition">
                    <span>Tài liệu & SOP</span>
                    <span class="text-xs bg-stone-300 px-1.5 py-0.5 rounded text-stone-600">0</span>
                </a>
                <a href="#" class="sidebar-item active flex items-center justify-between px-3 py-2.5 rounded-lg text-stone-900 transition">
                    <span>Nhân sự & đối tác</span>
                    <span id="badge-count" class="text-xs bg-stone-300 px-1.5 py-0.5 rounded text-stone-800 font-semibold">5</span>
                </a>
            </nav>
        </div>

        <!-- Sidebar Footer -->
        <div class="p-4 border-t border-stone-300 text-xs space-y-3 bg-[#eae6dc]/50">
            <div class="flex items-center space-x-2 text-emerald-600 font-medium">
                <span class="w-2 h-2 rounded-full bg-emerald-500 inline-block"></span>
                <span>Đã đồng bộ · cập nhật tức thì</span>
            </div>
            <div class="pt-2 border-t border-stone-300 space-y-1">
                <div class="font-bold text-stone-900">HOA</div>
                <div class="text-stone-500">Xem toàn bộ ·</div>
                <div class="text-stone-600 truncate">hoasbb@gmail.com</div>
            </div>
            <div class="grid grid-cols-2 gap-1 pt-1">
                <button class="bg-white border border-stone-300 text-stone-700 py-1.5 px-2 rounded hover:bg-stone-50 text-[11px] font-medium transition">Đổi mật khẩu</button>
                <button class="bg-white border border-stone-300 text-stone-700 py-1.5 px-2 rounded hover:bg-stone-50 text-[11px] font-medium transition">Thực hành</button>
                <button class="bg-white border border-stone-300 text-stone-700 py-1.5 px-2 rounded hover:bg-stone-50 text-[11px] font-medium transition">Bảo mật 2 lớp</button>
                <button class="bg-white border border-stone-300 text-stone-700 py-1.5 px-2 rounded hover:bg-stone-50 text-[11px] font-medium transition">Cài app</button>
            </div>
            <button class="w-full bg-white border border-stone-300 text-stone-700 py-1.5 rounded hover:bg-stone-50 text-xs font-medium transition flex items-center justify-center space-x-1">
                <span>Đăng xuất</span>
            </button>
        </div>
    </aside>

    <!-- Main Content -->
    <main class="flex-1 flex flex-col overflow-y-auto bg-[#f7f6f3]">
        <!-- Top Header Banner -->
        <div class="p-8 pb-4 border-b border-stone-200">
            <h1 class="text-2xl font-bold text-stone-900 tracking-tight">Nhân sự & đối tác</h1>
            <p class="text-sm text-stone-600 mt-1">Nhân viên nội bộ, thầu phụ, nhà cung cấp – dùng để giao việc và gắn người phụ trách.</p>
        </div>

        <!-- Controls Toolbar (Search, Filter, Add Button) -->
        <div class="px-8 py-4 flex flex-wrap items-center justify-between gap-4">
            <div class="flex items-center space-x-3 w-full md:w-auto flex-1 max-w-xl">
                <!-- Filter Dropdown -->
                <div class="relative">
                    <select id="filter-category" onchange="renderTable()" class="appearance-none bg-white border border-stone-300 text-stone-800 text-sm rounded-lg px-4 py-2 pr-8 focus:outline-none focus:ring-1 focus:ring-stone-400 font-medium cursor-pointer shadow-sm">
                        <option value="Tất cả">Tất cả phân loại</option>
                        <option value="Nội bộ">Nội bộ</option>
                        <option value="Thầu phụ">Thầu phụ</option>
                        <option value="Nhà cung cấp">Nhà cung cấp</option>
                    </select>
                    <div class="pointer-events-none absolute inset-y-0 right-0 flex items-center px-2 text-stone-500">
                        <i class="fa-solid fa-chevron-down text-xs"></i>
                    </div>
                </div>

                <!-- Search Input -->
                <div class="relative flex-1">
                    <span class="absolute inset-y-0 left-0 flex items-center pl-3 pointer-events-none text-stone-400">
                        <i class="fa-solid fa-search text-xs"></i>
                    </span>
                    <input type="text" id="search-input" oninput="renderTable()" placeholder="Tìm kiếm theo tên, chức danh, email, SĐT..." class="w-full bg-white border border-stone-300 text-stone-800 text-sm rounded-lg pl-9 pr-4 py-2 focus:outline-none focus:ring-1 focus:ring-stone-400 shadow-sm">
                </div>
            </div>

            <!-- Add Button -->
            <button onclick="openModal()" class="bg-stone-900 hover:bg-stone-800 text-white font-medium text-sm px-4 py-2 rounded-lg shadow transition flex items-center space-x-2">
                <i class="fa-solid fa-plus text-xs"></i>
                <span>Thêm nhân sự / đối tác</span>
            </button>
        </div>

        <!-- Data Table Container -->
        <div class="px-8 pb-12 flex-1">
            <div class="bg-white border border-stone-200 rounded-xl shadow-sm overflow-hidden">
                <div class="overflow-x-auto">
                    <table class="w-full text-left border-collapse text-sm">
                        <thead>
                            <tr class="bg-stone-100/70 border-b border-stone-200 text-stone-500 text-[11px] font-semibold tracking-wider uppercase">
                                <th class="py-3.5 px-6">Họ tên / Đơn vị</th>
                                <th class="py-3.5 px-4">Chức danh</th>
                                <th class="py-3.5 px-4">Phân loại</th>
                                <th class="py-3.5 px-4">Liên hệ</th>
                                <th class="py-3.5 px-4 text-center">Việc đang mở</th>
                                <th class="py-3.5 px-4 text-center">Dự án phụ trách</th>
                                <th class="py-3.5 px-4">Tình trạng</th>
                                <th class="py-3.5 px-6 text-right">Thao tác</th>
                            </tr>
                        </thead>
                        <tbody id="table-body" class="divide-y divide-stone-100 text-stone-800">
                            <!-- Rows will be injected dynamically -->
                        </tbody>
                    </table>
                </div>
                <!-- Empty State -->
                <div id="empty-state" class="hidden p-12 text-center text-stone-500">
                    <i class="fa-regular fa-folder-open text-3xl mb-2"></i>
                    <p>Không tìm thấy nhân sự hoặc đối tác phù hợp.</p>
                </div>
            </div>
        </div>
    </main>

    <!-- Modal Thêm/Sửa Nhân sự & Đối tác -->
    <div id="person-modal" class="fixed inset-0 bg-black/50 backdrop-blur-sm z-50 flex items-center justify-center hidden">
        <div class="bg-white rounded-2xl shadow-2xl w-full max-w-lg mx-4 overflow-hidden border border-stone-200 transform transition-all">
            <div class="px-6 py-4 border-b border-stone-200 flex items-center justify-between bg-stone-50">
                <h3 id="modal-title" class="font-bold text-lg text-stone-900">Thêm nhân sự & đối tác mới</h3>
                <button onclick="closeModal()" class="text-stone-400 hover:text-stone-600 transition p-1 rounded-lg">
                    <i class="fa-solid fa-xmark text-lg"></i>
                </button>
            </div>
            <form id="person-form" onsubmit="handleFormSubmit(event)" class="p-6 space-y-4">
                <input type="hidden" id="edit-index" value="-1">
                <div>
                    <label class="block text-xs font-semibold uppercase tracking-wider text-stone-600 mb-1">Họ tên / Đơn vị *</label>
                    <input type="text" id="input-name" required placeholder="Ví dụ: NGUYỄN THỊ MỸ LINH" class="w-full bg-stone-50 border border-stone-300 rounded-lg px-3.5 py-2 text-sm focus:outline-none focus:ring-2 focus:ring-stone-900 uppercase">
                </div>
                <div class="grid grid-cols-2 gap-4">
                    <div>
                        <label class="block text-xs font-semibold uppercase tracking-wider text-stone-600 mb-1">Chức danh</label>
                        <input type="text" id="input-role" placeholder="Ví dụ: ACC, PM, DES, DIR..." class="w-full bg-stone-50 border border-stone-300 rounded-lg px-3.5 py-2 text-sm focus:outline-none focus:ring-2 focus:ring-stone-900">
                    </div>
                    <div>
                        <label class="block text-xs font-semibold uppercase tracking-wider text-stone-600 mb-1">Phân loại</label>
                        <select id="input-category" class="w-full bg-stone-50 border border-stone-300 rounded-lg px-3.5 py-2 text-sm focus:outline-none focus:ring-2 focus:ring-stone-900">
                            <option value="Nội bộ">Nội bộ</option>
                            <option value="Thầu phụ">Thầu phụ</option>
                            <option value="Nhà cung cấp">Nhà cung cấp</option>
                        </select>
                    </div>
                </div>
                <div class="grid grid-cols-2 gap-4">
                    <div>
                        <label class="block text-xs font-semibold uppercase tracking-wider text-stone-600 mb-1">Số điện thoại</label>
                        <input type="text" id="input-phone" placeholder="0936008128" class="w-full bg-stone-50 border border-stone-300 rounded-lg px-3.5 py-2 text-sm focus:outline-none focus:ring-2 focus:ring-stone-900">
                    </div>
                    <div>
                        <label class="block text-xs font-semibold uppercase tracking-wider text-stone-600 mb-1">Email</label>
                        <input type="email" id="input-email" placeholder="example@gmail.com" class="w-full bg-stone-50 border border-stone-300 rounded-lg px-3.5 py-2 text-sm focus:outline-none focus:ring-2 focus:ring-stone-900">
                    </div>
                </div>
                <div class="grid grid-cols-2 gap-4">
                    <div>
                        <label class="block text-xs font-semibold uppercase tracking-wider text-stone-600 mb-1">Việc đang mở</label>
                        <input type="number" id="input-open-tasks" min="0" value="0" class="w-full bg-stone-50 border border-stone-300 rounded-lg px-3.5 py-2 text-sm focus:outline-none focus:ring-2 focus:ring-stone-900">
                    </div>
                    <div>
                        <label class="block text-xs font-semibold uppercase tracking-wider text-stone-600 mb-1">Dự án phụ trách</label>
                        <input type="number" id="input-projects" min="0" value="0" class="w-full bg-stone-50 border border-stone-300 rounded-lg px-3.5 py-2 text-sm focus:outline-none focus:ring-2 focus:ring-stone-900">
                    </div>
                </div>
                <div>
                    <label class="block text-xs font-semibold uppercase tracking-wider text-stone-600 mb-1">Tình trạng</label>
                    <select id="input-status" class="w-full bg-stone-50 border border-stone-300 rounded-lg px-3.5 py-2 text-sm focus:outline-none focus:ring-2 focus:ring-stone-900">
                        <option value="Đang làm việc">Đang làm việc</option>
                        <option value="Tạm nghỉ">Tạm nghỉ</option>
                        <option value="Đã nghỉ việc">Đã nghỉ việc</option>
                    </select>
                </div>
                <div class="pt-4 border-t border-stone-200 flex items-center justify-end space-x-3">
                    <button type="button" onclick="closeModal()" class="bg-white border border-stone-300 text-stone-700 px-4 py-2 rounded-lg text-sm font-medium hover:bg-stone-50 transition">Hủy</button>
                    <button type="submit" class="bg-stone-900 text-white px-5 py-2 rounded-lg text-sm font-medium hover:bg-stone-800 transition shadow">Lưu lại</button>
                </div>
            </form>
        </div>
    </div>

    <!-- JavaScript Application Logic -->
    <script>
        // Initial dataset matching the exact sample image
        let personnelList = [
            {
                name: "NGUYỄN THỊ MỸ LINH",
                role: "ACC",
                category: "Nội bộ",
                phone: "0936008128",
                email: "linhnguyen230989@gmail.com",
                openTasks: 0,
                projects: 0,
                status: "Đang làm việc"
            },
            {
                name: "NGUYỄN VĂN HÓA",
                role: "PM",
                category: "Nội bộ",
                phone: "0978943053",
                email: "hoasbb@gmail.com",
                openTasks: 0,
                projects: 0,
                status: "Đang làm việc"
            },
            {
                name: "TẠ HOÀNG ĐẠT",
                role: "DIR",
                category: "Nội bộ",
                phone: "0866625868",
                email: "andy.ta.2610@gmail.com",
                openTasks: 0,
                projects: 0,
                status: "Đang làm việc"
            },
            {
                name: "TRẦN ANH TUẤN",
                role: "DES",
                category: "Nội bộ",
                phone: "0987299774",
                email: "anhtuankts88@gmail.com",
                openTasks: 0,
                projects: 0,
                status: "Đang làm việc"
            },
            {
                name: "TRẦN VĂN HUYNH",
                role: "DES",
                category: "Nội bộ",
                phone: "0983955695",
                email: "h2arch.vn@gmail.com",
                openTasks: 0,
                projects: 0,
                status: "Đang làm việc"
            }
        ];

        // Render table function based on current search and filter
        function renderTable() {
            const tbody = document.getElementById('table-body');
            const emptyState = document.getElementById('empty-state');
            const filterCategory = document.getElementById('filter-category').value;
            const searchQuery = document.getElementById('search-input').value.toLowerCase().trim();

            tbody.innerHTML = '';

            // Filter data
            const filtered = personnelList.filter(item => {
                const matchesCategory = (filterCategory === 'Tất cả' || item.category === filterCategory);
                const matchesSearch = item.name.toLowerCase().includes(searchQuery) ||
                                      item.role.toLowerCase().includes(searchQuery) ||
                                      item.phone.toLowerCase().includes(searchQuery) ||
                                      item.email.toLowerCase().includes(searchQuery);
                return matchesCategory && matchesSearch;
            });

            // Update badge count
            document.getElementById('badge-count').textContent = personnelList.length;

            if (filtered.length === 0) {
                emptyState.classList.remove('hidden');
                return;
            } else {
                emptyState.classList.add('hidden');
            }

            filtered.forEach((item, index) => {
                // Find actual index in original list for editing/deleting correctly
                const originalIndex = personnelList.indexOf(item);

                let statusBadgeClass = 'bg-emerald-100 text-emerald-800';
                if (item.status === 'Tạm nghỉ') statusBadgeClass = 'bg-amber-100 text-amber-800';
                if (item.status === 'Đã nghỉ việc') statusBadgeClass = 'bg-rose-100 text-rose-800';

                const tr = document.createElement('tr');
                tr.className = 'hover:bg-stone-50/80 transition border-b border-stone-100';
                tr.innerHTML = `
                    <td class="py-4 px-6 font-bold text-stone-900">${escapeHtml(item.name)}</td>
                    <td class="py-4 px-4 text-stone-700 font-medium">${escapeHtml(item.role)}</td>
                    <td class="py-4 px-4">
                        <span class="inline-block bg-stone-200/80 text-stone-800 text-xs px-2 py-0.5 rounded font-medium">${escapeHtml(item.category)}</span>
                    </td>
                    <td class="py-4 px-4 text-stone-600">
                        <div class="font-medium">${escapeHtml(item.phone)}</div>
                        <div class="text-xs text-stone-500">${escapeHtml(item.email)}</div>
                    </td>
                    <td class="py-4 px-4 text-center font-semibold text-stone-800">${item.openTasks}</td>
                    <td class="py-4 px-4 text-center font-semibold text-stone-800">${item.projects}</td>
                    <td class="py-4 px-4">
                        <span class="inline-flex items-center px-2.5 py-1 rounded-full text-xs font-semibold ${statusBadgeClass}">
                            ${escapeHtml(item.status)}
                        </span>
                    </td>
                    <td class="py-4 px-6 text-right space-x-2">
                        <button onclick="editPerson(${originalIndex})" class="text-stone-400 hover:text-stone-900 p-1.5 rounded hover:bg-stone-200 transition" title="Chỉnh sửa">
                            <i class="fa-solid fa-pen text-xs"></i>
                        </button>
                        <button onclick="deletePerson(${originalIndex})" class="text-stone-400 hover:text-rose-600 p-1.5 rounded hover:bg-stone-200 transition" title="Xóa">
                            <i class="fa-solid fa-trash text-xs"></i>
                        </button>
                    </td>
                `;
                tbody.appendChild(tr);
            });
        }

        // Open Modal for adding
        function openModal() {
            document.getElementById('modal-title').textContent = 'Thêm nhân sự & đối tác mới';
            document.getElementById('edit-index').value = '-1';
            document.getElementById('person-form').reset();
            document.getElementById('person-modal').classList.remove('hidden');
        }

        // Open Modal for editing
        function editPerson(index) {
            const item = personnelList[index];
            document.getElementById('modal-title').textContent = 'Chỉnh sửa nhân sự & đối tác';
            document.getElementById('edit-index').value = index;
            document.getElementById('input-name').value = item.name;
            document.getElementById('input-role').value = item.role;
            document.getElementById('input-category').value = item.category;
            document.getElementById('input-phone').value = item.phone;
            document.getElementById('input-email').value = item.email;
            document.getElementById('input-open-tasks').value = item.openTasks;
            document.getElementById('input-projects').value = item.projects;
            document.getElementById('input-status').value = item.status;
            document.getElementById('person-modal').classList.remove('hidden');
        }

        // Close Modal
        function closeModal() {
            document.getElementById('person-modal').classList.add('hidden');
        }

        // Handle Form Submit (Add or Update)
        function handleFormSubmit(event) {
            event.preventDefault();
            const index = parseInt(document.getElementById('edit-index').value);

            const newItem = {
                name: document.getElementById('input-name').value.toUpperCase().trim(),
                role: document.getElementById('input-role').value.trim(),
                category: document.getElementById('input-category').value,
                phone: document.getElementById('input-phone').value.trim(),
                email: document.getElementById('input-email').value.trim(),
                openTasks: parseInt(document.getElementById('input-open-tasks').value) || 0,
                projects: parseInt(document.getElementById('input-projects').value) || 0,
                status: document.getElementById('input-status').value
            };

            if (index === -1) {
                personnelList.push(newItem);
            } else {
                personnelList[index] = newItem;
            }

            closeModal();
            renderTable();
        }

        // Delete person
        function deletePerson(index) {
            if (confirm('Bạn có chắc chắn muốn xóa nhân sự / đối tác này không?')) {
                personnelList.splice(index, 1);
                renderTable();
            }
        }

        // Helper function for security
        function escapeHtml(str) {
            if (!str) return '';
            return str.replace('&', '&amp;')
                      .replace('<', '&lt;')
                      .replace('>', '&gt;')
                      .replace('"', '&quot;')
                      .replace("'", '&#039;');
        }

        // Initial render on load
        window.onload = function() {
            renderTable();
        };
    </script>
</body>
</html>
