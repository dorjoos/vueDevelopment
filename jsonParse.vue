```
<template>
  <div>
    <p>this is dorjooasdsad {{ users }}</p>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    msg: String
  },
  data() {
    return {
      users: {
        list: [
          {
            name: "Dorjsambuu",
            id: 1,
            avatar: "/images/portrait/small/avatar-s-11.jpg",
            todo: [
              {
                id: 4,
                title: "tes",
                desc: "stet"
              },
              {
                id: 5,
                title: "asd",
                desc: "sadsad"
              },
              {
                id: 11,
                title: "Pick up Natasha 😁",
                desc:
                  "Sweet roll toffee dragée cotton candy jelly beans halvah gingerbread jelly-o. Ice cream bear claw sugar plum powder."
              },
              {
                id: 10,
                title: "Skype Tommy",
                desc:
                  "Tart oat cake sesame snaps lollipop croissant cake biscuit."
              },
              {
                id: 8,
                title: "Fix Responsiveness 💻",
                desc:
                  "Jelly topping toffee bear claw. Sesame snaps lollipop macaroon croissant cheesecake pastry cupcake."
              },
              {
                id: 6,
                title: "wetst",
                desc: "sfsd as"
              }
            ]
          },
          {
            name: "Zulsaran",
            id: 2,
            avatar: "/images/portrait/small/avatar-s-2.jpg",
            todo: [
              {
                id: 13,
                title: "dsadsa",
                desc: "tsagaanbolor"
              },
              {
                id: 12,
                title: "ereere",
                desc: "sdasdsasasasas asasasasas asasasasasasa"
              }
            ]
          }
        ]
      }
    };
  },
  created() {
    var jsonStr = '{"list":[]}';
    var keys = Object.keys(this.users["list"]);
    for (var i = 0; i < keys.length; i++) {
      var usr = this.users["list"][keys[i]]["name"];
      //console.log(this.users["list"][keys[i]]["name"], usr);
      var todoKey = Object.keys(this.users["list"][keys[i]]["todo"]);
      for (var j = 0; j < todoKey.length; j++) {
        var title = this.users["list"][keys[i]]["todo"][todoKey[j]]["title"];
        var desc = this.users["list"][keys[i]]["todo"][todoKey[j]]["desc"];
        var obj = JSON.parse(jsonStr);
        obj["list"].push({ name: usr, title: title, desc: desc });
        jsonStr = JSON.stringify(obj);
      }
    }
    jsonStr = JSON.stringify(obj);
    console.log(jsonStr);
  }
};
</script>
 
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
```
