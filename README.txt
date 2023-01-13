✋Json-Server:
    Json server is an npm package that lets you create fake REST APIs with zero coding.

    As a front end developer, I constantly need mock data that I can use to quickly prototype frontend component.

    Data should be fetchd asynchronously and the APIs should support not just GET but also POST PUT and DELETE requests.

    Creating a node + express + mongodb backend is pretty time consuming.

✋ REST APIs.
    (REpresentational State Trensfer Application Programming Interface)

    It is a software that allows two application to communicate with each other over the internet an through various devices. Every time you access an app like Facebook or check the weather on you smartphone, an API is used.

    A RESTful API is an architectural style () for an application program interface (API) that uses HTTP requests to access and use data. REST is not a programming language.

    (Means simple api ko hm restful api main convert krny k lyiea REST ka use karty hyn, Restfull API hoit ha means HTTP k sath jis k sath hm kam kr sakty hyn.)

    HTTP methods:
    CREATE =====> POST    
    REAT   =====> GET     
    UPDATE =====> PUT / PATCH (Agr hm put use karty hyn to complete sara data update ho jata ha or Patch main just utna part he update hota jis ko hm update karna chahty hyn. baki same rahta ha.)  
    DELETE =====> DELETE


    Previous method:
    POST    /api/crateUser
    GET    /api/readUsers
    UPDATE    /api/updateUser
    DELETE    /api/deleteUsers
        Ya purana trika ha. or agr hm restfull api use karty hyn to hamry end point change ni hoty.

    New method:
    POST  /api/user 
    GET   /api/user
    PATCH /api/user
    DELETE /api/user 

✋Steps:
1. First I Inetialize node package manager 
    npm init -y
2. npm install json-server
3. Add run script in Package.json file serve-json
4. npm run serve-json
5. filter product :  http://localhost:3000/products?category=electronics
6. nested filter:  http://localhost:3000/products&discount.type=shipping
7. sorting Data:  http://localhost:3000/products?_sort=price
8. sorting in decending order:  http://localhost:3000/products?_sort=price&_order=desc
9. if some field have same price. then sort them by other field:  http://localhost:3000/products?_sort=price,category&_order=desc,asc
10. pagination:  http://localhost:3000/products?_page=1&_limit=2
11. range of vlaue:  http://localhost:3000/products?price_gte=2000&price_lte=5000
12. not equel: http://localhost:3000/products?id_ne=2
13. like: http://localhost:3000/products?category_like=^f
14. full text search: http://localhost:3000/products?q=in
15. RelationShips: chield to parent http://localhost:3000/products?_embed=reviews
16. http://localhost:3000/products/1?_embed=reviews
17. Relationship Parent to chield: http://localhost:3000/reviews?_expand=product
18. Post Data: Install ThunderClient app in vscode 
19. POST PUT PATCH DELETE GET (test these all through thunderclient when create or update data the enter data in body in json formate)
20. Port Configration: By default json server run on 3000 port number. in package.json in script we add "serve-json": "json-server --watch db.json --port 4000"
21. Custom route configration: create routes.json file then "serve-json": "json-server --watch db.json --port 4000 --routes routes.json" http://localhost:4000/api/v1/products/electronics
22. create data.js & comment script in package.json file and add new script

23. Note: we can use these three libraries for realistic data generate.
    https://github.com/faker-js/faker
    https://github.com/boo1ean/casual
    https://github.com/chancejs/chancejs

24. create fake data and update package.json script