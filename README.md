# sfd4_generation_training
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
    <style>
      body {
        background-color: aqua;
        margin-left: 150px;
      }
      
      h1{
        margin-top: 5%;
text-align: center;

      }
      div{
        margin-top: 2%;
      }
      
       
    </style>
  </head>
  <body>
    <form name="index" onsubmit="return bookTicket()" action="" method="post">
      <h1>Booking Details</h1>
      <div>
        <input
          type="radio"
          name="one"
          id="One_Way"
          value="oneWay"
          onclick="checkButton()"/>One Way &nbsp;&nbsp; &nbsp; &nbsp;
        <input
          type="radio"
          name="one"
          id="Round_Way"
          value="roundWay"
          onclick=" checkButton()"
        />Round Trip<br />
        <br />
        </div>
    <div>
        <label for="from">From:</label>
        <input type="text" id="from" />&nbsp;&nbsp;
        <label for="to">To:</label>
        <input type="text" id="to" /><br /><br />
        <label for="depature">Depature:</label>
        <input type="date" id="depatureDate" />&nbsp;&nbsp;
        <label for="return">Return Date:</label>
        <input type="date" id="returnDate" />

    </div>
    <div>
        <h3>Number of Passengers</h3>
        <label for="adult">Adult</label>
        <input type="text" id="adult" />&nbsp;&nbsp;
        <label for="children">Children</label>
        <input type="text" id="children" /><br /><br />

    </div>
    <div>
        <h4>Passenger 1 details</h4>
        <label for="name">Name:</label>
        <input type="text" id="name1" />&nbsp;&nbsp;

        <input type="radio" name="gender" id="male" />Male&nbsp;&nbsp;&nbsp;&nbsp;
        <input type="radio" name="gender" id="female" />Female&nbsp;&nbsp;&nbsp;&nbsp;
        <label for="age">Age:</label>
        <input type="text" id="age" />&nbsp;&nbsp;<br />
    </div>
    <div>
        <h4>Passenger 2 details</h4>
        <label for="name">Name:</label>
        <input type="text" id="name2" />&nbsp;&nbsp;

        <input type="radio" name="gender" id="male" />Male&nbsp;&nbsp;&nbsp;&nbsp;
        <input type="radio" name="gender" id="female" />Female&nbsp;&nbsp;&nbsp;&nbsp;
        <label for="age">Age:</label>
        <input type="text" id="age" />&nbsp;&nbsp;
    </div>
        <h4>Contact Details</h4>
        <label for="contactName">Full Name:</label>
        <input type="text" id="contactName" />&nbsp;&nbsp;
        <label for="email">Email Id:</label>
        <input type="text" id="email" />&nbsp;&nbsp;
        <label for="mobile">Mobile #:</label>
        <input type="text" id="mobile" />&nbsp;&nbsp;<br /><br />

        <input
          type="reset"
          id="submit"
          value="Submit" 
          
          onclick="return bookTicket()"
        />
      </div>
    </form>
    <script>
      function bookTicket() {
        let fromValue = document.getElementById("from").value;
        let toValue = document.getElementById("to").value;

        if (
          fromValue == "null" ||
          fromValue == "" ||
          toValue == "null" ||
          toValue == ""
        ) {
          alert("From and To should not be blank");

          return false;
        }
        if (document.getElementById("One_Way").checked){
        let depatureDateValue = document.getElementById("depatureDate").value;
        if (depatureDateValue == "") {
          alert("Please Select Depature Date");
        }
    } else if (document.getElementById("Round_Way").checked) {
          let returnDateValue = document.getElementById("returnDate").value;
          if (returnDateValue == "") {
            alert("Please Select Return Date");
          }
        }

        let passengerName1 = document.index.name1.value;
        let passengerName2 = document.index.name2.value;

        if (passengerName1.length < 5 && passengerName2.length < 5) {
          alert("passenger name should be more than 5 character");
          return false;
        }

        

        

        let mymail = document.getElementById("email").value;
        let attherate = mymail.indexOf("@");
        let atthedot = mymail.lastIndexOf(".");
        if (
          attherate < 1 ||
          atthedot < attherate + 2 ||
          atthedot >= mymail.length
        ) {
          alert("enter the correct email");
          return false;
        }

        let mobile1 = document.getElementById("mobile").value;

        if (mobile1.length == 10) {
          return true;
        } else {
          alert("enter the correct 10 digits number");
          return false;
        }
      }
    </script>

  </body>
</html>
