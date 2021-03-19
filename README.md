# CUHK__SHOP__HTML-CSS-JS

### DOM Manipultion 
User Experience 
1. Dispplay products dynamically ( JSON / using php to import mysql table) 
2. Adding Product to the cart 
3. Local Storage ( cart info would not disappear when reload the webpage)
4. Calculate the total amount 

#### Products 
If we want to display the product from a json file 
- design a Product class first 
```
class Products{
   async getProducts(){
   //async function to fetch product 
   try{
      let result = await fetch("products.json");
      let data = result.json();  //data in json format 
      let products = data.items;  //object -> array 
      products = products.map(item => {
         const {name, price} = item.fields;
         const {id} = item.sys;
         const image = item.fields.image.fields.file.url;
         return {name, price, id, image}
       })
       return products;   //return array of products [name, price, id, image]
      } catch(error){
      console.log(error);
      }
     }
   }
   ```
       
      
      
