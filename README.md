# REACTS-POPUPS-ON-SCREEN-SHOW-

## bahot se tarike hai par model wala easy hai 
### 4 steps me popups taiyaar

#### overlay model usestate openmodel closedmodel (main part hai )

```react.js

import React, { useState } from "react";

function App() {
  // Step 1: State to control modal visibility
  const [showModal, setShowModal] = useState(false);

  // Step 2: Functions to handle modal open and close
  const openModal = () => setShowModal(true);
  const closeModal = () => setShowModal(false);

  return (
    <div className="App">
// button cretate karna pdega
      {/* Button to Open Modal */}
      <button onClick={openModal}>Open Modal</button>

same model for any bas ui jaisa chaiyeh vaise code likhe
      {/* Step 4: Modal */}
      {showModal && (
        <div style={styles.overlay}>
          <div style={styles.modal}>
            <h2>Modal Title</h2>
            <p>This is the modal content.</p>
            <button onClick={closeModal}>Close</button>
          </div>
        </div>
      )}


    </div>
  );
}

// Step 3: Styles for Modal and Overlay
const styles = {
  overlay: {
    position: "fixed",
    top: 0,
    left: 0,
    width: "100%",
    height: "100%",
    backgroundColor: "rgba(0, 0, 0, 0.5)",
    display: "flex",
    justifyContent: "center",
    alignItems: "center",
  },
  modal: {
    backgroundColor: "#fff",
    padding: "20px",
    borderRadius: "8px",
    boxShadow: "0 2px 10px rgba(0, 0, 0, 0.3)",
    textAlign: "center",
    minWidth: "300px",
  },
};

export default App;

```

### another same for some example 


```
import React, { useState } from "react";

function App() {
  // State to control the visibility of popup
  const [showPopup, setShowPopup] = useState(false);

  return (
    <div>
      {/* Button to Open Popup */}
      <button onClick={() => setShowPopup(true)}>Show Popup</button>

      {/* Popup Code */}
      {showPopup && (
        <div style={styles.overlay}>
          <div style={styles.popup}>
            <h2>Popup Content</h2>
            <p>This is a sample popup.</p>
            <button onClick={() => setShowPopup(false)}>Close</button>
          </div>
        </div>
      )}
    </div>
  );
}

// Styles for Popup and Overlay
const styles = {
  overlay: {
    position: "fixed",
    top: 0,
    left: 0,
    width: "100%",
    height: "100%",
    backgroundColor: "rgba(0, 0, 0, 0.5)",
    display: "flex",
    justifyContent: "center",
    alignItems: "center",
  },
  popup: {
    backgroundColor: "#fff",
    padding: "20px",
    borderRadius: "8px",
    boxShadow: "0 2px 10px rgba(0, 0, 0, 0.3)",
    textAlign: "center",
    minWidth: "300px",
  },
};

export default App;
```


# upar wla bhi mst working hai 
### example of real life use 
#### image ki upar laagaya hai 
```react.js
import React, { useState } from "react";
import { useNavigate } from "react-router-dom";

const PreviewUserManagement = () => {
  const navigate = useNavigate();

  const userDetails = {
    name: "John Doe",
    contact: "237468372",
    location: "New York",
    gender: "Male",
    status: "Active",
    emailId: "123bhu@gamil.com",
  };

  const restaurantBookings = [
    {
      id: 1,
      name: "The Grand Feast",
      eventType: "Birthday Party",
      eventDate: "2024-11-15 8:30 PM",
      amount: "$500",
      location: "Downtown, NY",
      noOfGuests: 25,
    },
  ];

  const [showModal, setShowModal] = useState(false);

  const openModal = () => setShowModal(true);
  const closeModal = () => setShowModal(false);

  return (
    <div className="p-6 bg-gray-100 min-h-screen">
      {/* Back Button */}
      <div className="mb-4">
        <button
          onClick={() => navigate(-1)}
          className="text-blue-600 hover:text-blue-800 font-semibold flex items-center gap-2"
        >
          <i className="fas fa-arrow-left"></i> Back
        </button>
      </div>

      {/* Page Title */}
      <h1 className="text-4xl font-bold text-center mb-6">User Details</h1>

      {/* User Details Section */}
      <div className="bg-white p-6 rounded-lg shadow-md mb-8">
        <h2 className="text-2xl font-semibold text-gray-700 mb-4">
          Profile Details
        </h2>
        <div className="grid grid-cols-2 gap-4">
          <div>
            <p className="text-gray-600 font-medium">Name:</p>
            <p className="text-gray-800">{userDetails.name}</p>
          </div>
          <div>
            <p className="text-gray-600 font-medium">Contact:</p>
            <p className="text-gray-800">{userDetails.contact}</p>
          </div>
          <div>
            <p className="text-gray-600 font-medium">Location:</p>
            <p className="text-gray-800">{userDetails.location}</p>
          </div>
          <div>
            <p className="text-gray-600 font-medium">Email Id:</p>
            <p className="text-gray-800">{userDetails.emailId}</p>
          </div>
          <div>
            <p className="text-gray-600 font-medium">Gender:</p>
            <p className="text-gray-800">{userDetails.gender}</p>
          </div>
          <div>
            <p className="text-gray-600 font-medium">Status:</p>
            <p
              className={`rounded px-2 py-1 text-white ${
                userDetails.status === "Active"
                  ? "bg-green-500"
                  : "bg-red-500"
              }`}
            >
              {userDetails.status}
            </p>
          </div>
          <div>
            <p className="text-gray-600 font-medium">Profile Picture:</p>
            <img
              onClick={openModal}
              src="https://via.placeholder.com/150"
              alt="Profile Picture"
              className="w-20 h-20 rounded-full object-cover cursor-pointer"
            />
          </div>
          {showModal && (
            <div style={styles.overlay}>
              <div style={styles.modal}>
                <img
                  src="https://via.placeholder.com/150"
                  alt="Profile Picture"
                  className="w-70 h-70 rounded object-cover"
                />
                <button
                  onClick={closeModal}
                  className="mt-4 px-4 py-2 bg-red-500 text-white rounded hover:bg-red-600"
                >
                  Close
                </button>
              </div>
            </div>
          )}
        </div>
      </div>

      {/* Restaurant Bookings Section */}
      <div className="bg-white p-6 rounded-lg shadow-md">
        <h2 className="text-2xl font-semibold text-gray-700 mb-4">
          Restaurants Booked by User
        </h2>
        <div className="overflow-x-auto">
          <table className="min-w-full bg-white border-collapse border border-gray-200">
            <thead>
              <tr className="bg-gray-200">
                <th className="p-3 border border-gray-300 text-left">
                  Restaurant Name
                </th>
                <th className="p-3 border border-gray-300 text-left">
                  Event Type
                </th>
                <th className="p-3 border border-gray-300 text-left">
                  Event Date
                </th>
                <th className="p-3 border border-gray-300 text-left">Amount</th>
                <th className="p-3 border border-gray-300 text-left">
                  Location
                </th>
                <th className="p-3 border border-gray-300 text-left">
                  No. of Guests
                </th>
              </tr>
            </thead>
            <tbody>
              {restaurantBookings.map((booking) => (
                <tr key={booking.id} className="hover:bg-gray-100">
                  <td className="p-3 border border-gray-300">{booking.name}</td>
                  <td className="p-3 border border-gray-300">
                    {booking.eventType}
                  </td>
                  <td className="p-3 border border-gray-300">
                    {booking.eventDate}
                  </td>
                  <td className="p-3 border border-gray-300">
                    {booking.amount}
                  </td>
                  <td className="p-3 border border-gray-300">
                    {booking.location}
                  </td>
                  <td className="p-3 border border-gray-300">
                    {booking.noOfGuests}
                  </td>
                </tr>
              ))}
            </tbody>
          </table>
        </div>
      </div>
    </div>
  );
};

const styles = {
  overlay: {
    position: "fixed",
    top: 0,
    left: 0,
    width: "100%",
    height: "100%",
    backgroundColor: "rgba(0, 0, 0, 0.5)",
    display: "flex",
    justifyContent: "center",
    alignItems: "center",
  },
  modal: {
    backgroundColor: "#fff",
    padding: "10px",
    borderRadius: "8px",
    boxShadow: "0 2px 10px rgba(0, 0, 0, 0.3)",
    textAlign: "center",
    minWidth: "300px",
  },
};

export default PreviewUserManagement;


```




