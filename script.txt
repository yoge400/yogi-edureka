class restaurantManager{ //1
    restaurantList = [{ //2
        id: 1,
        restaurantName: 'KFC',
        address: 'Anand Vihar',
        city: 'Delhi'
    },
    {
        id: 2,
        restaurantName: 'Domino',
        address: 'Savita Vihar',
        city: 'Delhi'
    },
    {
        id: 3,
        restaurantName: 'Burger King',
        address: 'Civil Lines',
        city: 'Pune'
    },
    {
        id: 4,
        restaurantName: 'Subway',
        address: 'Cantonment',
        city: 'Mumbai'
    }];

      printAllRestaurantNames = () => { //3
        return this.restaurantList.map(restaurant => restaurant.restaurantName);
      }

      filterRestaurantsByCity = (cityname) => { //4
        return this.restaurantList.filter(restaurant => restaurant.city == cityname)
      }
}

const restautantObject = new restaurantManager();

const output1 = restautantObject.printAllRestaurantNames();
console.log(output1);

console.log(restautantObject.filterRestaurantsByCity("Delhi"));

orderData = {
    'Below 500': 20,
    '500-1000': 29,
    '1000-1500': 30,
    '1500-2000': 44,
    'Above 2000': 76
};

//a 

const total = Object.values(orderData).reduce((prev, next) => prev + next );
console.log(total);

//b

const headers = Object.keys(orderData);
console.log(headers);

//c 
let arr = [];
const response = headers.map((item, index) => {
      const obj = {
          'id' : index + 1,
          'order': item,
          'orderpercentage' : ((orderData[item]/total )*100).toFixed(2),   //( 20 / 199) * 100
          'restaurant': 'Punjabi Tadka'
      }
      arr.push(obj);
})

console.log(arr);


