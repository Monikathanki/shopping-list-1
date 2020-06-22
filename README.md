# Shopping List App Challenge

This repo conta'use strict';

const STORE = [
  {id: cuid(), name: "apples", checked: false},
  {id: cuid(), name: "oranges", checked: false},
  {id: cuid(), name: "milk", checked: true},
  {id: cuid(), name: "bread", checked: false}
];


function generateItemElement(item) {
  return `
    <li data-item-id="${item.id}">
      <span class="shopping-item js-shopping-item ${item.checked ? "shopping-item__checked" : ''}">${item.name}</span>
      <div class="shopping-item-controls">
        <button class="shopping-item-toggle js-item-toggle">
            <span class="button-label">check</span>
        </button>
        <button class="shopping-item-delete js-item-delete">
            <span class="button-label">delete</span>
        </button>
      </div>
    </li>`;
}


function generateShoppingItemsString(shoppingList) {
  console.log("Generating shopping list element");

  const items = shoppingList.map((item) => generateItemElement(item));
  
  return items.join("");
}


function renderShoppingList() {
  // render the shopping list in the DOM
  console.log('`renderShoppingList` ran');
  const shoppingListItemsString = generateShoppingItemsString(STORE);

  // insert that HTML into the DOM
  $('.js-shopping-list').html(shoppingListItemsString);
}


function handleNewItemSubmit() {
  // target text entry input and store the new item submitted by the user into a new variable

	// generate a new list element using the new item submitted above

	// render the shopping list in the DOM with the new item
  console.log('`handleNewItemSubmit` ran');
}


function handleItemCheckClicked() {
  // listen for when the 'check' button is clicked

	// iterate through the STORE and target the item whose respective button was clicked

	// change value of 'checked' to its opposite

	// render the shopping list in the DOM

  console.log('`handleItemCheckClicked` ran');
}


function handleDeleteItemClicked() {
  // listen for when the 'delete' button is clicked

	// iterate through the STORE and target the item whose respective button was clicked

	// remove the item from the STORE

	// render the shopping list in the DOM

  console.log('`handleDeleteItemClicked` ran')
}

// this function will be our callback when the page loads. it's responsible for
// initially rendering the shopping list, and activating our individual functions
// that handle new item submission and user clicks on the "check" and "delete" buttons
// for individual shopping list items.
function handleShoppingList() {
  renderShoppingList();
  handleNewItemSubmit();
  handleItemCheckClicked();
  handleDeleteItemClicked();

}

// when the page loads, call `handleShoppingList`
$(handleShoppingList);ins starter files for the *Shopping List App* challenge.
