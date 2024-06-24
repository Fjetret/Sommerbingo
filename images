const tasks = Array.from({ length: 15 }, (_, i) => i);  // Just creating a simple array to loop over

function initializeBingoGrid(bingoId) {
    const bingoGrid = document.getElementById('bingoGrid');
    const savedState = JSON.parse(localStorage.getItem(bingoId) || '[]');

    tasks.forEach((_, index) => {
        const square = document.createElement('div');
        square.className = 'bingo-square';

        if (savedState[index]) {
            square.classList.add('completed');
        }

        square.addEventListener('click', () => {
            square.classList.toggle('completed');
            saveBingoState(bingoId);
        });

        bingoGrid.appendChild(square);
    });
}

function saveBingoState(bingoId) {
    const bingoGrid = document.getElementById('bingoGrid');
    const state = Array.from(bingoGrid.children).map(square => 
        square.classList.contains('completed')
    );

    localStorage.setItem(bingoId, JSON.stringify(state));
}
