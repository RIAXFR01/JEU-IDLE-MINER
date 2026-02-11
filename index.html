let gems = 0;
let gemsPerClick = 1;
let gemsPerSec = 0;

const items = [
    { id: 'pickaxe', name: '⛏️ Pioche', cost: 10, owned: 0, production: 1 },
    { id: 'drill', name: '🔨 Foreuse', cost: 100, owned: 0, production: 8 },
    { id: 'excavator', name: '🚜 Excavatrice', cost: 1000, owned: 0, production: 47 },
    { id: 'mine', name: '🏗️ Mine', cost: 11000, owned: 0, production: 260 },
    { id: 'factory', name: '🏭 Usine', cost: 120000, owned: 0, production: 1400 },
    { id: 'robot', name: '🤖 Robot', cost: 1300000, owned: 0, production: 7800 },
    { id: 'ai', name: '🧠 IA', cost: 14000000, owned: 0, production: 44000 }
];

function format(num) {
    if (num >= 1e12) return (num / 1e12).toFixed(1) + 'T';
    if (num >= 1e9) return (num / 1e9).toFixed(1) + 'B';
    if (num >= 1e6) return (num / 1e6).toFixed(1) + 'M';
    if (num >= 1e3) return (num / 1e3).toFixed(1) + 'K';
    return Math.floor(num);
}

function getCost(item) {
    return Math.floor(item.cost * Math.pow(1.15, item.owned));
}

function updateDisplay() {
    document.getElementById('gems').textContent = format(gems);
    document.getElementById('perClick').textContent = format(gemsPerClick);
    document.getElementById('perSec').textContent = format(gemsPerSec);
    updateShop();
}

function updateShop() {
    items.forEach(item => {
        const cost = getCost(item);
        const canBuy = gems >= cost;
        
        const btn = document.getElementById('btn-' + item.id);
        const ownedSpan = document.getElementById('owned-' + item.id);
        
        if (btn && ownedSpan) {
            btn.textContent = format(cost) + ' 💎';
            btn.disabled = !canBuy;
            ownedSpan.textContent = item.owned;
        }
    });
}

function renderShop() {
    const container = document.getElementById('shopItems');
    container.innerHTML = '';

    items.forEach(item => {
        const cost = getCost(item);
        const canBuy = gems >= cost;

        const div = document.createElement('div');
        div.className = 'shop-item';

        const info = document.createElement('div');
        info.className = 'shop-item-info';
        info.innerHTML = `
            <div class="shop-item-name">${item.name}</div>
            <div class="shop-item-desc">+${format(item.production)}/sec</div>
        `;

        const buyBtn = document.createElement('button');
        buyBtn.id = 'btn-' + item.id;
        buyBtn.className = 'shop-item-buy';
        buyBtn.textContent = format(cost) + ' 💎';
        buyBtn.disabled = !canBuy;
        buyBtn.onclick = () => buyItem(item.id);

        const owned = document.createElement('span');
        owned.id = 'owned-' + item.id;
        owned.className = 'owned';
        owned.textContent = item.owned;

        div.appendChild(info);
        div.appendChild(owned);
        div.appendChild(buyBtn);
        container.appendChild(div);
    });
}

function buyItem(id) {
    const item = items.find(i => i.id === id);
    const cost = getCost(item);

    if (gems >= cost) {
        gems -= cost;
        item.owned++;
        calculateProduction();
        updateDisplay();
    }
}

function calculateProduction() {
    gemsPerSec = 0;
    items.forEach(item => {
        gemsPerSec += item.owned * item.production;
    });
}

document.getElementById('mineBtn').onclick = () => {
    gems += gemsPerClick;
    updateDisplay();
};

setInterval(() => {
    if (gemsPerSec > 0) {
        gems += gemsPerSec / 10;
        updateDisplay();
    }
}, 100);

setInterval(() => {
    localStorage.setItem('mineIdle', JSON.stringify({
        gems,
        items: items.map(i => ({ id: i.id, owned: i.owned }))
    }));
}, 3000);

window.onload = () => {
    const save = localStorage.getItem('mineIdle');
    if (save) {
        const data = JSON.parse(save);
        gems = data.gems || 0;
        if (data.items) {
            data.items.forEach(saved => {
                const item = items.find(i => i.id === saved.id);
                if (item) item.owned = saved.owned;
            });
        }
        calculateProduction();
    }
    renderShop();
    updateDisplay();
};
