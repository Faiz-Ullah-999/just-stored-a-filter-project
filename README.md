<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Fruits & Veggies – Vitamins</title>
    <script src="https://cdn.tailwindcss.com"></script>
  </head>
  <body class="bg-gray-100 min-h-screen p-6 font-sans">
    <div class="max-w-7xl mx-auto">
      <h1 class="text-3xl font-bold text-center text-green-700 mb-6">
        🥦 Fruits & Vegetables – Vitamins
      </h1>

      <div class="flex flex-wrap justify-center gap-4 mb-8">
        <button
          onclick="renderItems('all')"
          class="bg-gray-600 text-white px-4 py-2 rounded hover:bg-gray-700"
        >
          Show All
        </button>
        <button
          onclick="renderItems('A')"
          class="bg-orange-500 text-white px-4 py-2 rounded hover:bg-orange-600"
        >
          Vitamin A
        </button>
        <button
          onclick="renderItems('C')"
          class="bg-yellow-500 text-white px-4 py-2 rounded hover:bg-yellow-600"
        >
          Vitamin C
        </button>
        <button
          onclick="renderItems('K')"
          class="bg-green-500 text-white px-4 py-2 rounded hover:bg-green-600"
        >
          Vitamin K
        </button>
        <button
          onclick="renderItems('Zinc')"
          class="bg-blue-500 text-white px-4 py-2 rounded hover:bg-blue-600"
        >
          Zinc
        </button>
      </div>

      <div
        id="vitaminContainer"
        class="grid grid-cols-1 sm:grid-cols-3 lg:grid-cols-4 gap-6"
      ></div>
    </div>

    <script>
      const items = [
        { name: "Orange", type: "Fruit", vitamins: ["C"] },
        { name: "Mango", type: "Fruit", vitamins: ["A", "C"] },
        { name: "Banana", type: "Fruit", vitamins: ["B6", "C"] },
        { name: "Apple", type: "Fruit", vitamins: ["C"] },
        { name: "Papaya", type: "Fruit", vitamins: ["A", "C"] },
        { name: "Avocado", type: "Fruit", vitamins: ["K", "E", "C", "B5"] },
        { name: "Blueberries", type: "Fruit", vitamins: ["C", "K"] },
        { name: "Watermelon", type: "Fruit", vitamins: ["A", "C"] },
        { name: "Kiwi", type: "Fruit", vitamins: ["C", "K", "E"] },
        { name: "Pineapple", type: "Fruit", vitamins: ["C", "B1"] },

        { name: "Carrot", type: "Vegetable", vitamins: ["A", "K"] },
        { name: "Spinach", type: "Vegetable", vitamins: ["A", "C", "K"] },
        { name: "Broccoli", type: "Vegetable", vitamins: ["C", "K", "A"] },
        { name: "Kale", type: "Vegetable", vitamins: ["A", "C", "K"] },
        { name: "Sweet Potato", type: "Vegetable", vitamins: ["A", "C"] },
        { name: "Red Bell Pepper", type: "Vegetable", vitamins: ["C", "A"] },
        { name: "Tomato", type: "Vegetable", vitamins: ["C", "A", "K"] },
        { name: "Cabbage", type: "Vegetable", vitamins: ["C", "K"] },
        { name: "Peas", type: "Vegetable", vitamins: ["A", "K", "C"] },
        { name: "Pumpkin", type: "Vegetable", vitamins: ["A", "C", "E"] },
      ];

      const renderItems = (filter = "all") => {
        const container = document.getElementById("vitaminContainer");

        const filtered =
          filter === "all"
            ? items
            : items.filter((item) => item.vitamins.includes(filter));

        container.innerHTML = filtered
          .map(
            (item) => `
        <div class="bg-white border rounded-lg shadow-md p-5 hover:shadow-xl transition">
          <h2 class="text-xl font-bold text-gray-800">${item.name}</h2>
          <p class="text-sm text-gray-500 mb-2">${item.type}</p>
          <p class="text-gray-700">Vitamins: <span class="font-semibold">${item.vitamins.join(
            ", "
          )}</span></p>
        </div>
      `
          )
          .join("");
      };

      renderItems();
    </script>
  </body>
</html>
