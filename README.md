# REACTS-POPUPS-ON-SCREEN-SHOW-

## bahot se tarike hai par model wala easy hai 
### 4 steps me popups taiyaar

```react


import React, { useState } from "react";

function App() {
  // State for modal visibility
  const [showModal, setShowModal] = useState(false);

  // State for form fields
  const [formData, setFormData] = useState({
    name: "",
    email: "",
  });

  // Function to handle form input changes
  const handleChange = (e) => {
    const { name, value } = e.target;
    setFormData({
      ...formData,
      [name]: value,
    });
  };

  // Function to handle form submission
  const handleSubmit = (e) => {
    e.preventDefault();
    console.log("Form Submitted:", formData);
    // Close the modal after submission
    setShowModal(false);
  };

  return (
    <div className="App">
      {/* Button to open modal */}
      <button onClick={() => setShowModal(true)}>Open Form Modal</button>

      {/* Modal */}
      {showModal && (
        <div style={styles.overlay}>
          <div style={styles.modal}>
            <h2>Fill the Form</h2>
            <form onSubmit={handleSubmit}>
              <div>
                <label>Name:</label>
                <input
                  type="text"
                  name="name"
                  value={formData.name}
                  onChange={handleChange}
                  required
                />
              </div>
              <div>
                <label>Email:</label>
                <input
                  type="email"
                  name="email"
                  value={formData.email}
                  onChange={handleChange}
                  required
                />
              </div>
              <button type="submit">Submit</button>
              <button
                type="button"
                onClick={() => setShowModal(false)}
                style={{ marginLeft: "10px" }}
              >
                Cancel
              </button>
            </form>
          </div>
        </div>
      )}
    </div>
  );
}

// Styles for Modal and Overlay
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



