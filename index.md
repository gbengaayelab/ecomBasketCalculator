<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.4.1/css/bootstrap.min.css">
    <title>Ecommerce Calculator</title>
</head>
<body>
    <div class="row">
        <div class="col-sm-2 m-3 p-3"></div>
        <div class="col-sm-6 m-4 p-4">
            <div class="border text-center"> 
                <div class="jumbotron p-3 m-3 border rounded border-prilightmary justify-content-center">
                <h2 class="display:2">Basket Size for Groceries?</h2>
            <form>
                <div class="form-group">
                    <label for="Price">Price</label>
                    <input type="text" class="form-control text-left price_input" name="price" value="500"> 
                <div class="form-group">
                    <label for="quantity" class="text-left" name="quantity">
                        Quantity
                        <span class="badge badge-primary quantityLabelRange">1</span>
                    </label>
                    <input type="range" class="form-control border border-primary rounded quantity_input" value="1"
                    min="1" max="100" name="quantity">
            </form>
            <div class="text-right text-primary"><h3 class="display:3 total_price"></h3></div>
                </div>
                </div>
                </div>
        <div class="col-sm-3 m-3 p-3"></div>
        </div>

    </div>
      
  
    <script>
        // Grab Everything I need
        const priceGrabber= document.querySelector('.price_input'); //OR const priceGrabber= document.querySelector('[name=price]');
        const quantityGrabber= document.querySelector('.quantity_input'); //OR const priceGrabber= document.querySelector('[name=quantity]');
        const totalPriceGrabber= document.querySelector('.total_price');
        const labelGrabber= document.querySelector('.quantityLabelRange');

        
        


        // Create all the functions needed
        const calCulateCost = () =>{
            const price =priceGrabber.value;
            const quantity=quantityGrabber.value;
            const totalPrice= price*quantity;
                       
            totalPriceGrabber.innerText=`${totalPrice.toFixed(2)} NGN`;
        }
        const quantityLabelShow = () =>{
            const quantity=quantityGrabber.value;
             labelGrabber.innerText=quantity;

        }
        // Add event listeners
        priceGrabber.addEventListener('input', calCulateCost);  // Event listener for changing the Total Cost on input of price
        quantityGrabber.addEventListener('input', calCulateCost); //Event listener for changing the Total Cost on input of Quantity
        quantityGrabber.addEventListener('input', quantityLabelShow);

        //on Run first
        calCulateCost();

    </script>
</body>
</html>
