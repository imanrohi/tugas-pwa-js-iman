const data_product = [
  {
    _id: "202209122001",
    index: 0,
    isActive: true,
    price: "Rp 750.000",
    picture: "image/youth.jpg",
    color: "Black",
    name: "Youth",
    description: "Topi Anak"
  },
  {
    _id: "202209122001",
    index: 1,
    isActive: true,
    price: "Rp 550.000",
    picture: "image/sport.jpg",
    color: "Black",
    name: "Sport",
    description: "Topi Anak"
  },
  {
    _id: "202209122002",
    index: 2,
    isActive: true,
    price: "Rp 950.000",
    picture: "image/gap.jpg",
    color: "Blue",
    name: "Gap",
    description: "Topi Anak"
  },
  {
    _id: "202209122003",
    index: 3,
    isActive: true,
    price: "Rp 450.000",
    picture: "image/catenzo.jpg",
    color: "Red",
    name: "Catenzo",
    description: "Topi Anak"
  },
  {
    _id: "202209122004",
    index: 4,
    isActive: true,
    price: "Rp 470.000",
    picture: "image/caraka.jpg",
    color: "Black",
    name: "Caraka",
    description: "Topi Anak"
  },
  {
    _id: "202209122005",
    index: 5,
    isActive: true,
    price: "Rp 880.000",
    picture: "image/blue.jpg",
    color: "Blue",
    name: "Blue",
    description: "Topi Anak"
  }
];
showDataProduct(data_product);
function showDataProduct(data_product) {
  let item_html = "";
  data_product.forEach((product, index) => {
    item_html += `
        <tr>
            <td>${index + 1}</td>
            <td>${product.name}</td>
            <td>${product.color}</td>
            <td>${product.price}</td>
            <td>${product.description}</td>
            <td>
                <button class="btn btn-sm btn-danger" onclick="editPeserta('${
                  product._id
                }')">Edit</button>
            </td>
            <td>
                <button class="btn btn-sm btn-danger" onclick="deletePeserta('${
                  product._id
                }')">Delete</button>
            </td>
        </tr>
    `;
  });
  let table_body_product = document.getElementById("data_product");
  table_body_product.innerHTML = item_html;
  console.log(table_body_product.attributes);
}
searchTable(data_product);
function searchTable(data_product) {
  var newarray = [];
  document.getElementById("mySearch").addEventListener("keyup", function () {
    var search = this.value.toLowerCase();
    newarray = data_product.filter(function (val, index) {
      if (
        val.name.includes(search) ||
        val.color.includes(search) ||
        val.description.includes(search)
      ) {
        var newobj = {
          name: val.name,
          color: val.color,
          description: val.description
        };
        return newobj;
      }
    });
    showDataProduct(newarray);
  });
}
