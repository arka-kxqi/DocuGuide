
# DocuGuide

## Project Description
DocuGuide is a website designed to assist first-generation, low-income (FGLI) students and anyone in need of affordable legal assistance in navigating complex legal documents. Whether dealing with immigration forms, employment documents, FAFSA applications, rental agreements, or various contracts, legal counsel can be prohibitively expensive. FGLI students and low/middle-class individuals often face the daunting task of navigating the complexities of the U.S. legal system alone, leading to potential risks such as signing predatory contracts or incorrectly filling out crucial forms.

DocuGuide simplifies the process of understanding and creating important legal documents by summarizing sections, defining difficult terms, and generating filled documents based on provided information (such as personal details or an outline).

## Inspiration
This project was inspired by our personal experiences as first-generation students with immigrant parents from India. We witnessed firsthand the challenges our families faced in understanding and completing complex forms without adequate guidance. These experiences highlighted the need for a tool to bridge the gap and provide much-needed support. By creating DocuGuide, we aim to empower students and individuals like us, ensuring they have the resources and confidence to navigate the legal system.

## What It Does
- **Definitions:** Helps users understand complex legal terms in documents such as immigration paperwork, contracts, or the FAFSA.
- **Document Generation:** Creates legal documents tailored to the user’s specific needs and provided information.
- **Document Summarization:** Provides concise summaries of sections within a document, ensuring users understand the content and requirements.
- **Automatic Clarifications:** Highlights potential areas of concern, including loopholes and confusing sections in the document summaries.

## How We Built It
DocuGuide is powered by an Express.js server and utilizes EJS as the view engine for dynamic page rendering. This server-side rendering approach enhances performance, reflected in our perfect Lighthouse score. We use a combination of CSS and JavaScript files tailored to specific page needs, ensuring optimal performance and accessibility. Client-side JavaScript powers features like text replacement on hover, dynamic size adjustments, and our "highlight to define" functionality, which utilizes a dictionary API.

For the document summarization feature, we use OpenAI's GPT-4o-mini model. The uploaded document is processed into smaller sections based on common legal section dividers using custom regular expressions. Each section is then summarized and analyzed for potential pitfalls. This section-based approach enhances the accuracy and relevance of the AI's output.

For document generation, we pass the document title and user-provided information to the AI model, which generates a draft document. Users can review and edit the generated document before summarizing it for better understanding.

Our custom-built authentication system securely manages user accounts and document access, using hashing, salting, and Firebase for data storage.

## Challenges We Ran Into
- **Chunking:** Ensuring accurate and efficient document sectioning without doubling AI token usage.
- **Model Safeguards:** Overcoming OpenAI's restrictions on generating legal documents through prompt engineering.
- **Resizing Boxes:** Preventing layout jitter by dynamically adjusting section box sizes.
- **Storing Data Securely:** Transitioning from insecure plain-text storage to a secure, persistent database solution.

## Accomplishments That We're Proud Of
- **Intuitive Site:** Our website is stylish, accessible, and highly performant, with a perfect Lighthouse score.
- **No Cost for the User:** We optimized costs to avoid charging users or displaying ads.
- **Highly Accurate Chunking:** Our custom chunking algorithm ensures precise, section-specific summaries.
- **Flexibility:** Users can choose how they upload documents, provide information, and save their work.
- **Account/Document System:** Our secure, custom-built account system allows for seamless document access and storage.

## What We Learned
- **Importance of Data Privacy and Security:** We implemented strict measures to protect user data and sensitive information.
- **Prompt Engineering:** We honed our skills in crafting prompts to elicit useful responses from AI models.
- **Hosting Considerations:** We evaluated and selected the best hosting platform for our needs, ultimately choosing Vercel.
- **Routing and Safely Storing User Data:** We learned how to securely manage user authentication and data storage using Firebase and bcrypt.

## What's Next
- **Performance Improvements:** We plan to experiment with different AI models and refine prompts to further enhance speed.
- **Form Walkthroughs:** We intend to add step-by-step guidance for filling out common forms like the FAFSA.
- **Document Chat:** We plan to integrate a chat feature for users to ask questions about their documents.
- **Google Account Compatibility:** We aim to offer Google account login options to simplify the sign-in process.

## File Structure
- **api/** - API folder
- **index.js** - Express server
- **views/** - EJS files
  - **pages/** - Pages
  - **partials/** - Templates (head, navbar, footer)
- **public/** - Resources
  - **css/** - CSS files
  - **js/** - JavaScript files
  - **media/** - Images, icons, and manifests

## Local Setup
1. Clone the repository.
2. Run `npm install`.
3. Set up a `.env` file.
4. Add your own `OPENAI_API_KEY` to the `.env` file.
5. Add your own `FIREBASE_SERVICE_ACCOUNT_KEY` to the `.env` file.
6. Run `node .` in the root directory.
7. Open `localhost:3000` to preview the application.

https://legal-lieutenant.vercel.app/