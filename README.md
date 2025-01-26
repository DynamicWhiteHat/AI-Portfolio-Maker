## Powered By:
<pre><a href="https://www.groq.com"><img src="https://raw.githubusercontent.com/RMNCLDYO/groq-ai-toolkit/main/.github/groq-logo.png" width=200></a>  </pre>


# AI Portfolio Maker
This is a simple AI portfolio creator powered by models from GROQ AI.
Asks for a user's information, then sends it to an AI to create a website

# Usage:
- Visit https://ai-portfolio-azure.vercel.app/
- Fill out the form and choose an AI model
  - I found the best models were llama3-70b-8192 and llama-3.1-8b-instant


# How it works
- Uses HTML to create form, which is handled by a JS backend. Once submitted, this backend sends a POST request to GROQ's backend with the following prompt:
<pre>

Create a highly professional and visually appealing portfolio website with advanced front-end development skills. 
It should not look overly simplistic or dated, but instead have a modern, clean design that reflects the quality of a 
hired front-end developer's work. The website should incorporate detailed context based on the information provided below, 
utilizing multiple sections, backgrounds, margins, paddings, and clear text visibility. Avoid generic designs by 
tailoring the layout to suit the provided preferences. Make use of shadows, animations, and polished design elements 
to ensure a standout presentation.

Please return the HTML code only. For styling, include the CSS within a <STYLE> tag in the <head> section, rather than linking to an external style.css.

Key Considerations:
- Prioritize text visibility: Ensure sufficient contrast between text and background (e.g., avoid white text on a white background).
- Use well-structured sections and content placement for a smooth flow.
- Include thoughtful use of margins, padding, and alignment to enhance the user experience.
</pre>
- The following parameters are then passed from the form:
<pre>
- Website Title: "${wname}"
- Person's Name: "${pname}"
- Their Interests: "${interests}"
- Descriptive Words: "${word1}, ${word2}, ${word3}"
- Website Style: "${style}"
- Main Colors: "${color1}, ${color2}, ${color3}"
</pre>
- This process is done 3 times, passing the current code every time. This attempts to make the website better, which works, although the end result is far from acceptable.



# IMPORTANT:
Make sure to allow pop-ups in your browser, otherwise it doesn't work right


# Note
More of a proof-of-concept than actual service, as the websites created lack any effort.


PS: It would be a lot faster if I didn't get rate limited, so the minimum time will always be 24 seconds.
