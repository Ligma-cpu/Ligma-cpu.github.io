<script>
  function openTab(tabId) {
    // Hide all tab contents
    document.querySelectorAll('.tab-content').forEach(tab => {
      tab.style.display = 'none';
    });

    // Show the selected tab
    const selectedTab = document.getElementById(tabId);
    if (selectedTab) selectedTab.style.display = 'block';
  }

  function openSubTab(subTabId) {
    // Hide all subtab contents
    document.querySelectorAll('.subtab-content').forEach(sub => {
      sub.style.display = 'none';
    });

    // Remove "active" class from all subtab buttons
    document.querySelectorAll('.subtab-buttons button').forEach(btn => {
      btn.classList.remove('active');
    });

    // Show selected subtab and mark its button as active
    const subTab = document.getElementById(subTabId);
    if (subTab) subTab.style.display = 'block';

    const btn = document.getElementById('btn-' + subTabId);
    if (btn) btn.classList.add('active');
  }

  function toggleReplies(el) {
    const replies = el.nextElementSibling.nextElementSibling;
    if (replies && replies.classList.contains('thread-replies')) {
      replies.style.display = (replies.style.display === 'none') ? 'block' : 'none';
    }
  }

  // Set default tabs when page loads
  document.addEventListener('DOMContentLoaded', function () {
    openTab('tab1');
    openSubTab('cs2');
  });
</script>
