# vue-project

This template should help get you started developing with Vue 3 in Vite.

## Recommended IDE Setup

[VSCode](https://code.visualstudio.com/) + [Volar](https://marketplace.visualstudio.com/items?itemName=Vue.volar) (and disable Vetur) + [TypeScript Vue Plugin (Volar)](https://marketplace.visualstudio.com/items?itemName=Vue.vscode-typescript-vue-plugin).

## Customize configuration

See [Vite Configuration Reference](https://vitejs.dev/config/).

## Project Setup

```sh
npm install
```

### Compile and Hot-Reload for Development

```sh
npm run dev
```

### Compile and Minify for Production

```sh
npm run build
```

### Lint with [ESLint](https://eslint.org/)

```sh
npm run lint
```
#   M a t u r a I T - S h o p 
 
 

Axios,TailwindCSS, Prettierrc, Postcss, definedProps, RestApi, onMounted,
Destruktyryzcja, use toFixed in rating, ref and reactive
Ref

<!-- /* fetch('https://fakestoreapi.com/products')
        .then(res=>res.json())
        .then(data=>console.log(data)) */

  /*       axios.get('https://fakestoreapi.com/products').then((res) => console.log(res.data)) */

  #npm install axios
  #npm install
  #npm run dev
 -->

  <!-- const sortProducts = () => {
    let sortedProducts = [...originalProducts]; 

    if (filters.sortBy === 'title') {
        sortedProducts.sort((a, b) => a.title.localeCompare(b.title));
    } else if (filters.sortBy === 'priceLow') {
        sortedProducts.sort((a, b) => a.price - b.price);
    } else if (filters.sortBy === 'priceHigh') {
        sortedProducts.sort((a, b) => b.price - a.price);
    }

    const searchQuery = filters.searchQuery.toLowerCase();
    products.value = sortedProducts.filter(
        product => product.title.toLowerCase().includes(searchQuery)
    );
}
To podejście eliminuje konieczność tworzenia kopii --> tablicy za każdym razem oraz wykorzystuje metody wbudowane w obiektach tablicy do sortowania, co potencjalnie może poprawić wydajność kodu.

W przypadku złożonych aplikacji lub większej ilości danych, optymalizacja może obejmować bardziej zaawansowane techniki, takie jak paginacja czy ładowanie danych w sposób asynchroniczny po części, aby zmniejszyć obciążenie strony.

Jeśli masz konkretne wymagania co do wydajności lub inne cele optymalizacji, konkretniejsza optymalizacja może być konieczna. Jeśli potrzebujesz pomocy z konkretnymi aspektami optymalizacji w kontekście swojej aplikacji, chętnie pomogę!