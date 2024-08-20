#Business Portal - Frontend Components

This repository contains the frontend components for the **Business Portal** project. These components handle various functionalities such as adding a new business, managing navigation, and supporting a clean and responsive UI.

## Components

### 1. `AddBusinessForm.js`

The `AddBusinessForm` component provides a form that allows users to submit their business information. This form handles various input fields like business name, description, contact information, address, and category. The data submitted by the user is sent to a backend API to be stored and processed.

**Key Features:**
- Controlled form inputs for handling business information.
- Client-side validation to ensure required fields are filled out.
- Asynchronous submission of form data to the API endpoint `http://localhost:4000/api/become-a-creator`.
- Conversion of the products input from a comma-separated string to an array.
- User feedback on form submission success or failure.

**Usage Example:**
javascript
import AddBusinessForm from './AddBusinessForm';

const MyComponent = () => {
    const handleBusinessAdded = (data) => {
        console.log('Business added:', data);
    };

    return <AddBusinessForm onBusinessAdded={handleBusinessAdded} />;
};


### 2. `BecomeSellerForm.js`

The `BecomeSellerForm` component is a more enhanced version of the `AddBusinessForm`, with additional styling and animations provided by `framer-motion`. It also includes a dropdown selection for the business category.

**Key Features:**
- Animated modal form using `framer-motion` for a smoother user experience.
- Dropdown select options for business categories (Retail, D2C, C2C).
- Themed styling with a gradient background for a more modern look.
- Closes the form modal upon successful submission or on user command.

**Usage Example:**
javascript
import BecomeSellerForm from './BecomeSellerForm';

const MyComponent = () => {
    const [isFormOpen, setIsFormOpen] = useState(false);

    return (
        <>
            <button onClick={() => setIsFormOpen(true)}>Become a Seller</button>
            {isFormOpen && <BecomeSellerForm onClose={() => setIsFormOpen(false)} />}
        </>
    );
};


### 3. `Navbar.js`

The `Navbar` component manages the top navigation bar for the application. It includes links to the main pages (`Home`, `About`) and buttons for actions such as opening the seller form and contacting the site administrators.

**Key Features:**
- Responsive navigation bar with mobile and desktop views.
- Integration with `BecomeSellerForm` to trigger the form modal.
- Smooth transitions and hover effects for an enhanced UI experience.

**Usage Example:**
javascript
import Navbar from './Navbar';

const MyComponent = () => {
    return <Navbar />;
};


### 4. `ReuseReduceRecycle.js`

The `ReuseReduceRecycle` component is a visually engaging section that displays information related to the sustainability theme of the website. It uses SVG graphics and a gradient background to highlight the importance of reusing, reducing, and recycling.

**Key Features:**
- SVG-based graphic with custom linear gradient styling.
- Full-screen section designed to grab the user's attention.

**Usage Example:**
javascript
import ReuseReduceRecycle from './ReuseReduceRecycle';

const MyComponent = () => {
    return <ReuseReduceRecycle />;
};


## Getting Started

To run the project locally:

1. Clone the repository.
2. Install dependencies using `npm install` or `yarn`.
3. Start the development server using `npm start` or `yarn start`.

Ensure that your backend API is running locally at `http://localhost:4000` to handle form submissions.
