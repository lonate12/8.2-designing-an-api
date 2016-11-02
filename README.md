# 8.2-designing-an-api
Designing an API using Apiary.io.

FORMAT: 1A
HOST: http://polls.apiblueprint.org/

# Majestic Thai

An API that allows stores menu items and stores orders for viewing on a kitchen view.

## Menu Items Collection [/rene-thai-menu-items]

### List All Menu Items [GET]

+ Response 200 (application/json)

        [
            {
                "_id": "5813c3a2a01f27000381c38b",
                "name": "Pad Thai",
                "price": 10.95,
                "category": "Specialties",
                "description": "Rice noodles stir-fried with chicken, shrimp, eggs, bean sprouts, scallions, peanuts and Pad Thai sauce. Served with a wedge of lime. (The National dish of Thailand)"
            },{
                ...
            }
        ]

## Menu Item [/rene-thai-menu-items/{id}]

Obtain information from one specific menu item using the id of the menu item.

+ Parameters

    + id - ID of the menu item in the form "_XXXXXXXXX..." where X are integers and letters in a MongoDB format.
    
### Get Individual Menu Item [GET]

+ Response 200 (application/json)

        {
            "_id": "5813c3a2a01f27000381c38b",
            "name": "Pad Thai",
            "price": 10.95,
            "category": "Specialties",
            "description": "Rice noodles stir-fried with chicken, shrimp, eggs, bean sprouts, scallions, peanuts and Pad Thai sauce. Served with a wedge of lime. (The National dish of Thailand)"
        }
        
## List of Orders [/rene-thai-orders]

Obtain a list of orders submitted by customers for view in the kitchen.

### Get Order List [GET]

+ Response 200 (application/json)

        [
            {
                _id: "5817fbc4feab6500036999e0",
                username: "New Order",
                time: "2016-11-01T02:19:48.057Z",
                total: 46.30,
                items: [
                    {
                    name: "Sweet Tea",
                    price: 1.95
                    },
                    {
                    name: "Coca-Cola",
                    price: 1.95
                    },
                    {
                    name: "Crispy Red Curry Duck",
                    price: 21.95
                    },
                    {
                    name: "Pad Thai",
                    price: 10.95
                    }
                ]
            },{
                ...
            }
        ]
        
## Individual Order [/rene-thai-orders/{id}]

Obtain an individual order submitted to the kitchen.

+ Parameters

    + id - ID of the order in the form "_XXXXXXXXX..." where X are integers and letters in a MongoDB format.
    
### Get Individual Order [GET]

+ Response 200 (application/json)

        {
            _id: "5817fbc4feab6500036999e0",
            username: "New Order",
            time: "2016-11-01T02:19:48.057Z",
            total: 46.30,
            items: [
                {
                name: "Sweet Tea",
                price: 1.95
                },
                {
                name: "Coca-Cola",
                price: 1.95
                },
                {
                name: "Crispy Red Curry Duck",
                price: 21.95
                },
                {
                name: "Pad Thai",
                price: 10.95
                }
            ]
        }
