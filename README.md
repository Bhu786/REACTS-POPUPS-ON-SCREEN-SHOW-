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







