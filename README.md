[MsJohnWebsite.html](https://github.com/user-attachments/files/23135794/MsJohnWebsite.html)
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ms. John's Chemistry Class</title>
    <style>
        /* Basic page setup and background styling */
        body {
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            margin: 0;
            padding: 0;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100%;
        }
        
        html {
            height: 100%;
        }

        /* Main container that centers content and sets max width */
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }

        /* Header section styling - the welcome banner at the top */
        .header {
            background: white;
            border-radius: 15px;
            padding: 30px;
            margin-bottom: 30px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
            text-align: center;
        }

        .header h1 {
            color: #2c3e50;
            margin: 0 0 10px 0;
            font-size: 2.5em;
        }

        .header p {
            color: #7f8c8d;
            margin: 0;
            font-size: 1.1em;
        }

        /* Tab navigation bar - creates the clickable tabs at the top */
        .tabs {
            display: flex;
            background: white;
            border-radius: 15px 15px 0 0;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
            margin-bottom: 0;
        }

        /* Individual tab button styling */
        .tab {
            flex: 1;
            padding: 20px;
            background: #ecf0f1;
            border: none;
            cursor: pointer;
            font-size: 16px;
            font-weight: 600;
            color: #34495e;
            transition: all 0.3s ease;
            border-right: 1px solid #bdc3c7;
        }

        .tab:last-child {
            border-right: none;
        }

        .tab.active {
            background: #3498db;
            color: white;
        }

        .tab:hover:not(.active) {
            background: #d5dbdb;
        }

        /* Main content area below the tabs */
        .content {
            background: white;
            border-radius: 0 0 15px 15px;
            padding: 30px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
            min-height: 500px;
        }

        /* Tab content containers - hidden by default */
        .tab-content {
            display: none;
        }

        /* Show only the active tab content */
        .tab-content.active {
            display: block;
        }

        /* Section titles within each tab */
        .section-title {
            color: #2c3e50;
            font-size: 1.8em;
            margin-bottom: 20px;
            border-bottom: 3px solid #3498db;
            padding-bottom: 10px;
        }

        /* Document upload area - where teachers can add new files */
        .document-upload {
            background: #f8f9fa;
            border: 2px dashed #3498db;
            border-radius: 10px;
            padding: 30px;
            text-align: center;
            margin-bottom: 30px;
        }

        .upload-btn {
            background: #3498db;
            color: white;
            border: none;
            padding: 12px 25px;
            border-radius: 8px;
            cursor: pointer;
            font-size: 16px;
            margin: 10px;
            transition: background 0.3s ease;
        }

        .upload-btn:hover {
            background: #2980b9;
        }

        /* Container for the list of uploaded documents */
        .document-list {
            margin-top: 20px;
        }

        /* Individual document item in the list */
        .document-item {
            background: #f8f9fa;
            border: 1px solid #e9ecef;
            border-radius: 8px;
            padding: 15px;
            margin-bottom: 10px;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        /* Document information section (icon + name + date) */
        .document-info {
            display: flex;
            align-items: center;
            gap: 15px;
        }

        /* File type icon (PDF, DOC, etc.) */
        .document-icon {
            width: 40px;
            height: 40px;
            background: #e74c3c;
            border-radius: 8px;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-weight: bold;
        }

        /* Container for View and Delete buttons */
        .document-actions {
            display: flex;
            gap: 10px;
        }

        /* View and Delete button styling */
        .view-btn, .delete-btn {
            padding: 8px 15px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            font-size: 14px;
            transition: all 0.3s ease;
        }

        .view-btn {
            background: #27ae60;
            color: white;
        }

        .view-btn:hover {
            background: #229954;
        }

        .delete-btn {
            background: #e74c3c;
            color: white;
        }

        .delete-btn:hover {
            background: #c0392b;
        }

        /* Text area where teachers can write class notes */
        .notes-area {
            width: 100%;
            min-height: 300px;
            border: 2px solid #e9ecef;
            border-radius: 10px;
            padding: 20px;
            font-size: 16px;
            font-family: inherit;
            resize: vertical;
            margin-bottom: 15px;
        }

        .notes-area:focus {
            outline: none;
            border-color: #3498db;
        }

        .save-btn {
            background: #27ae60;
            color: white;
            border: none;
            padding: 12px 25px;
            border-radius: 8px;
            cursor: pointer;
            font-size: 16px;
            transition: background 0.3s ease;
        }

        .save-btn:hover {
            background: #229954;
        }

        /* Grid layout for lesson cards - responsive columns */
        .lesson-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 20px;
            margin-top: 20px;
        }

        /* Individual lesson card styling */
        .lesson-card {
            background: #f8f9fa;
            border-radius: 10px;
            padding: 20px;
            border-left: 5px solid #3498db;
            transition: transform 0.3s ease;
        }

        .lesson-card:hover {
            transform: translateY(-5px);
        }

        .lesson-title {
            color: #2c3e50;
            font-size: 1.3em;
            margin-bottom: 10px;
        }

        .lesson-description {
            color: #7f8c8d;
            margin-bottom: 15px;
        }

        .lesson-meta {
            display: flex;
            justify-content: space-between;
            align-items: center;
            font-size: 14px;
            color: #95a5a6;
        }

        /* Modal popup for viewing documents - covers entire screen */
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0,0,0,0.5);
            z-index: 1000;
        }

        /* The actual content box inside the modal */
        .modal-content {
            background: white;
            margin: 5% auto;
            padding: 30px;
            border-radius: 15px;
            width: 80%;
            max-width: 800px;
            max-height: 80%;
            overflow-y: auto;
        }

        .modal-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 20px;
            border-bottom: 2px solid #ecf0f1;
            padding-bottom: 15px;
        }

        .close-btn {
            background: none;
            border: none;
            font-size: 24px;
            cursor: pointer;
            color: #7f8c8d;
        }

        .close-btn:hover {
            color: #2c3e50;
        }

        /* Document content display area inside modal */
        .document-viewer {
            background: #f8f9fa;
            border: 1px solid #e9ecef;
            border-radius: 8px;
            padding: 30px;
            min-height: 400px;
            font-family: 'Courier New', monospace;
            line-height: 1.6;
        }

        /* Teacher-only sections (highlighted in yellow) */
        .admin-panel {
            background: #fff3cd;
            border: 1px solid #ffeaa7;
            border-radius: 8px;
            padding: 15px;
            margin-bottom: 20px;
        }

        .admin-title {
            color: #856404;
            font-weight: bold;
            margin-bottom: 10px;
        }

        @media (max-width: 768px) {
            .tabs {
                flex-direction: column;
            }
            
            .tab {
                border-right: none;
                border-bottom: 1px solid #bdc3c7;
            }
            
            .tab:last-child {
                border-bottom: none;
            }
            
            .lesson-grid {
                grid-template-columns: 1fr;
            }
            
            .modal-content {
                width: 95%;
                margin: 10% auto;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <header class="header">
            <h1>🧪 Ms. Johnson's Chemistry Class</h1>
            <p>Welcome to our interactive chemistry learning platform</p>
        </header>

        <div class="tabs">
            <button class="tab active" onclick="showTab('documents')">📄 Documents</button>
            <button class="tab" onclick="showTab('notes')">📝 Notes</button>
            <button class="tab" onclick="showTab('lessons')">🎓 Lessons</button>
            <button class="tab" onclick="showTab('assignments')">📋 Assignments</button>
        </div>

        <div class="content">
            <!-- Documents Tab -->
            <div id="documents" class="tab-content active">
                <h2 class="section-title">Class Documents</h2>
                
                <div class="admin-panel">
                    <div class="admin-title">Teacher Panel</div>
                    <div class="document-upload">
                        <h3>📤 Upload New Document</h3>
                        <p>Select a document to share with your students (view-only)</p>
                        <input type="file" id="fileInput" accept=".pdf,.doc,.docx,.txt" style="display: none;">
                        <button class="upload-btn" onclick="document.getElementById('fileInput').click()">Choose File</button>
                        <button class="upload-btn" onclick="uploadDocument()">Upload Document</button>
                    </div>
                </div>

                <div class="document-list" id="documentList">
                    <!-- Sample documents -->
                    <div class="document-item">
                        <div class="document-info">
                            <div class="document-icon">PDF</div>
                            <div>
                                <div><strong>Periodic Table Reference</strong></div>
                                <div style="color: #7f8c8d; font-size: 14px;">Uploaded 2 days ago</div>
                            </div>
                        </div>
                        <div class="document-actions">
                            <button class="view-btn" onclick="viewDocument('Periodic Table Reference', 'This is a comprehensive periodic table reference guide with detailed information about each element, including atomic numbers, atomic masses, electron configurations, and chemical properties.')">View</button>
                            <button class="delete-btn" onclick="deleteDocument(this)">Delete</button>
                        </div>
                    </div>
                    
                    <div class="document-item">
                        <div class="document-info">
                            <div class="document-icon">DOC</div>
                            <div>
                                <div><strong>Chemical Bonding Notes</strong></div>
                                <div style="color: #7f8c8d; font-size: 14px;">Uploaded 1 week ago</div>
                            </div>
                        </div>
                        <div class="document-actions">
                            <button class="view-btn" onclick="viewDocument('Chemical Bonding Notes', 'Chapter 1: Introduction to Chemical Bonding\n\nChemical bonding is the process by which atoms combine to form compounds. There are three main types of chemical bonds:\n\n1. Ionic Bonds\n- Formed between metals and non-metals\n- Electrons are transferred from one atom to another\n- Results in charged ions\n\n2. Covalent Bonds\n- Formed between non-metals\n- Electrons are shared between atoms\n- Can be single, double, or triple bonds\n\n3. Metallic Bonds\n- Found in metals\n- Electrons form a \"sea\" around metal cations\n- Allows for conductivity and malleability')">View</button>
                            <button class="delete-btn" onclick="deleteDocument(this)">Delete</button>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Notes Tab -->
            <div id="notes" class="tab-content">
                <h2 class="section-title">Class Notes & Announcements</h2>
                
                <div class="admin-panel">
                    <div class="admin-title">Teacher Panel - Add Notes</div>
                    <textarea class="notes-area" id="teacherNotes" placeholder="Add class notes, announcements, or important information for students...">📢 Welcome to Chemistry Class!

Important Reminders:
• Lab safety goggles are required for all experiments
• Quiz on Chapter 3 (Atomic Structure) scheduled for Friday
• Science fair project proposals due next Monday

Today's Lesson: Chemical Reactions
We'll be covering the different types of chemical reactions and how to balance equations.

Homework: Complete problems 1-15 on page 87</textarea>
                    <br>
                    <button class="save-btn" onclick="saveNotes()">Save Notes</button>
                </div>

                <div style="margin-top: 30px;">
                    <h3>Student View:</h3>
                    <div id="studentNotesView" style="background: #f8f9fa; border-radius: 10px; padding: 20px; border-left: 5px solid #3498db; white-space: pre-wrap;">📢 Welcome to Chemistry Class!

Important Reminders:
• Lab safety goggles are required for all experiments
• Quiz on Chapter 3 (Atomic Structure) scheduled for Friday
• Science fair project proposals due next Monday

Today's Lesson: Chemical Reactions
We'll be covering the different types of chemical reactions and how to balance equations.

Homework: Complete problems 1-15 on page 87</div>
                </div>
            </div>

            <!-- Lessons Tab -->
            <div id="lessons" class="tab-content">
                <h2 class="section-title">Chemistry Lessons</h2>
                
                <div class="lesson-grid">
                    <div class="lesson-card">
                        <div class="lesson-title">⚛️ Atomic Structure</div>
                        <div class="lesson-description">Learn about protons, neutrons, electrons, and how atoms are organized.</div>
                        <div class="lesson-meta">
                            <span>Chapter 1</span>
                            <span>45 min</span>
                        </div>
                    </div>
                    
                    <div class="lesson-card">
                        <div class="lesson-title">🔗 Chemical Bonding</div>
                        <div class="lesson-description">Explore ionic, covalent, and metallic bonds and how they form compounds.</div>
                        <div class="lesson-meta">
                            <span>Chapter 2</span>
                            <span>60 min</span>
                        </div>
                    </div>
                    
                    <div class="lesson-card">
                        <div class="lesson-title">⚗️ Chemical Reactions</div>
                        <div class="lesson-description">Understanding different types of reactions and balancing chemical equations.</div>
                        <div class="lesson-meta">
                            <span>Chapter 3</span>
                            <span>50 min</span>
                        </div>
                    </div>
                    
                    <div class="lesson-card">
                        <div class="lesson-title">🧮 Stoichiometry</div>
                        <div class="lesson-description">Calculate quantities in chemical reactions using mole ratios.</div>
                        <div class="lesson-meta">
                            <span>Chapter 4</span>
                            <span>70 min</span>
                        </div>
                    </div>
                    
                    <div class="lesson-card">
                        <div class="lesson-title">💧 Solutions & Concentration</div>
                        <div class="lesson-description">Learn about molarity, dilutions, and solution preparation.</div>
                        <div class="lesson-meta">
                            <span>Chapter 5</span>
                            <span>55 min</span>
                        </div>
                    </div>
                    
                    <div class="lesson-card">
                        <div class="lesson-title">🌡️ Thermochemistry</div>
                        <div class="lesson-description">Study energy changes in chemical reactions and calorimetry.</div>
                        <div class="lesson-meta">
                            <span>Chapter 6</span>
                            <span>65 min</span>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Assignments Tab -->
            <div id="assignments" class="tab-content">
                <h2 class="section-title">Assignments & Homework</h2>
                
                <div class="lesson-grid">
                    <div class="lesson-card" style="border-left-color: #e74c3c;">
                        <div class="lesson-title">📝 Homework: Chapter 3 Problems</div>
                        <div class="lesson-description">Complete problems 1-15 on page 87. Focus on balancing chemical equations.</div>
                        <div class="lesson-meta">
                            <span style="color: #e74c3c;">Due: Tomorrow</span>
                            <span>15 problems</span>
                        </div>
                    </div>
                    
                    <div class="lesson-card" style="border-left-color: #f39c12;">
                        <div class="lesson-title">🧪 Lab Report: Acid-Base Titration</div>
                        <div class="lesson-description">Write a complete lab report including hypothesis, procedure, data, and conclusions.</div>
                        <div class="lesson-meta">
                            <span style="color: #f39c12;">Due: Friday</span>
                            <span>Lab Report</span>
                        </div>
                    </div>
                    
                    <div class="lesson-card" style="border-left-color: #27ae60;">
                        <div class="lesson-title">📊 Science Fair Project Proposal</div>
                        <div class="lesson-description">Submit your science fair project proposal with research question and methodology.</div>
                        <div class="lesson-meta">
                            <span style="color: #27ae60;">Due: Next Monday</span>
                            <span>Project Proposal</span>
                        </div>
                    </div>
                    
                    <div class="lesson-card" style="border-left-color: #9b59b6;">
                        <div class="lesson-title">📖 Reading: Organic Chemistry Basics</div>
                        <div class="lesson-description">Read Chapter 7 sections 7.1-7.3 and take notes on functional groups.</div>
                        <div class="lesson-meta">
                            <span style="color: #9b59b6;">Due: Next Week</span>
                            <span>Reading Assignment</span>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <!-- Document Viewer Modal -->
    <div id="documentModal" class="modal">
        <div class="modal-content">
            <div class="modal-header">
                <h2 id="modalTitle">Document Title</h2>
                <button class="close-btn" onclick="closeModal()">&times;</button>
            </div>
            <div class="document-viewer" id="documentContent">
                Document content will appear here...
            </div>
        </div>
    </div>

    <script>
        function showTab(tabName) {
            // Hide all tab contents
            const contents = document.querySelectorAll('.tab-content');
            contents.forEach(content => content.classList.remove('active'));
            
            // Remove active class from all tabs
            const tabs = document.querySelectorAll('.tab');
            tabs.forEach(tab => tab.classList.remove('active'));
            
            // Show selected tab content
            document.getElementById(tabName).classList.add('active');
            
            // Add active class to clicked tab
            event.target.classList.add('active');
        }

        function uploadDocument() {
            const fileInput = document.getElementById('fileInput');
            const file = fileInput.files[0];
            
            if (!file) {
                showNotification('Please select a file first!', 'error');
                return;
            }
            
            // Create new document item
            const documentList = document.getElementById('documentList');
            const documentItem = document.createElement('div');
            documentItem.className = 'document-item';
            
            const fileExtension = file.name.split('.').pop().toUpperCase();
            const fileName = file.name.replace(/\.[^/.]+$/, "");
            
            documentItem.innerHTML = `
                <div class="document-info">
                    <div class="document-icon">${fileExtension}</div>
                    <div>
                        <div><strong>${fileName}</strong></div>
                        <div style="color: #7f8c8d; font-size: 14px;">Uploaded just now</div>
                    </div>
                </div>
                <div class="document-actions">
                    <button class="view-btn" onclick="viewDocument('${fileName}', 'This document has been uploaded and is available for viewing. Content would be displayed here in a real implementation.')">View</button>
                    <button class="delete-btn" onclick="deleteDocument(this)">Delete</button>
                </div>
            `;
            
            documentList.appendChild(documentItem);
            fileInput.value = '';
            showNotification('Document uploaded successfully!', 'success');
        }

        function viewDocument(title, content) {
            document.getElementById('modalTitle').textContent = title;
            document.getElementById('documentContent').textContent = content;
            document.getElementById('documentModal').style.display = 'block';
        }

        function closeModal() {
            document.getElementById('documentModal').style.display = 'none';
        }

        function deleteDocument(button) {
            const documentItem = button.closest('.document-item');
            const fileName = documentItem.querySelector('strong').textContent;
            
            // Create inline confirmation
            const originalContent = documentItem.innerHTML;
            documentItem.innerHTML = `
                <div style="display: flex; align-items: center; justify-content: space-between; width: 100%;">
                    <span>Delete "${fileName}"?</span>
                    <div>
                        <button class="view-btn" onclick="confirmDelete(this)" style="margin-right: 10px;">Confirm</button>
                        <button class="delete-btn" onclick="cancelDelete(this, \`${originalContent.replace(/`/g, '\\`')}\`)">Cancel</button>
                    </div>
                </div>
            `;
        }

        function confirmDelete(button) {
            const documentItem = button.closest('.document-item');
            documentItem.remove();
            showNotification('Document deleted successfully!', 'success');
        }

        function cancelDelete(button, originalContent) {
            const documentItem = button.closest('.document-item');
            documentItem.innerHTML = originalContent;
        }

        function saveNotes() {
            const teacherNotes = document.getElementById('teacherNotes').value;
            document.getElementById('studentNotesView').textContent = teacherNotes;
            showNotification('Notes saved successfully!', 'success');
        }

        function showNotification(message, type) {
            const notification = document.createElement('div');
            notification.style.cssText = `
                position: fixed;
                top: 20px;
                right: 20px;
                padding: 15px 25px;
                border-radius: 8px;
                color: white;
                font-weight: bold;
                z-index: 1001;
                animation: slideIn 0.3s ease;
                background: ${type === 'success' ? '#27ae60' : '#e74c3c'};
            `;
            notification.textContent = message;
            
            document.body.appendChild(notification);
            
            setTimeout(() => {
                notification.remove();
            }, 3000);
        }

        // Close modal when clicking outside
        window.onclick = function(event) {
            const modal = document.getElementById('documentModal');
            if (event.target === modal) {
                closeModal();
            }
        }

        // Add CSS animation
        const style = document.createElement('style');
        style.textContent = `
            @keyframes slideIn {
                from { transform: translateX(100%); opacity: 0; }
                to { transform: translateX(0); opacity: 1; }
            }
        `;
        document.head.appendChild(style);
    </script>
<script>(function(){function c(){var b=a.contentDocument||a.contentWindow.document;if(b){var d=b.createElement('script');d.innerHTML="window.__CF$cv$params={r:'993b94db55c19acc',t:'MTc2MTMzMTAwNC4wMDAwMDA='};var a=document.createElement('script');a.nonce='';a.src='/cdn-cgi/challenge-platform/scripts/jsd/main.js';document.getElementsByTagName('head')[0].appendChild(a);";b.getElementsByTagName('head')[0].appendChild(d)}}if(document.body){var a=document.createElement('iframe');a.height=1;a.width=1;a.style.position='absolute';a.style.top=0;a.style.left=0;a.style.border='none';a.style.visibility='hidden';document.body.appendChild(a);if('loading'!==document.readyState)c();else if(window.addEventListener)document.addEventListener('DOMContentLoaded',c);else{var e=document.onreadystatechange||function(){};document.onreadystatechange=function(b){e(b);'loading'!==document.readyState&&(document.onreadystatechange=e,c())}}}})();</script></body>
</html>
