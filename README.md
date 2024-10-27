document.addEventListener('DOMContentLoaded', () => {
    let currentPage = 1;
    const totalPages = 4;
    const autoScrollDelay = 3000; // 3 seconds per page
    
    function showPage(pageNumber) {
        document.querySelectorAll('.page').forEach(page => {
            page.classList.add('hidden');
        });
        
        const currentPageElement = document.getElementById(`page${pageNumber}`);
        if (currentPageElement) {
            currentPageElement.classList.remove('hidden');
        }
    }
    
    function nextPage() {
        if (currentPage < totalPages) {
            currentPage++;
            showPage(currentPage);
        }
    }
    
    function startAutoScroll() {
        const interval = setInterval(() => {
            if (currentPage < totalPages) {
                nextPage();
            } else {
                clearInterval(interval);
            }
        }, autoScrollDelay);
    }
    
    const typingText = document.querySelector('.typing-text');
    function typeText(element, text) {
        let index = 0;
        element.textContent = '';
        
        function type() {
            if (index < text.length) {
                element.textContent += text.charAt(index);
                index++;
                setTimeout(type, 100);
            }
        }
        
        type();
    }
    
    document.addEventListener('keydown', (e) => {
        if (e.key === 'ArrowRight' || e.key === 'Space') {
            nextPage();
        }
    });
    
    document.addEventListener('click', () => {
        nextPage();
    });
    
    showPage(1);
    startAutoScroll();
    
    const targetDate = new Date('2025-06-24').getTime();
    
    function updateCountdown() {
        const now = new Date().getTime();
        const distance = targetDate - now;
        
        if (distance < 0) {
            document.querySelector('.date').textContent = 'TIME EXPIRED';
            return;
        }
    }
    
    updateCountdown();
});
