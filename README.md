AI Desk Object Sorter
Project Description

A Teachable Machine vision model that classifies batteries, watches, and coins using live webcam footage. The model was refined from an earlier prototype that included sunglasses, which was removed due to classification issues caused by hand occlusion and object scale.
Classes Identified

The model was trained to identify the following objects:

    Batteries – including AAA, AA, and 18650 cells

    Watches – with varied dials and straps (bright dial, blue dial, and black dial)

    Coins – dime, nickel, and quarter

Discussion & Reflection
1. Model Performance & Iteration

    The initial model was not very accurate. It was overly biased toward detecting hands in the frame, since larger objects like sunglasses required more hand-holding.

    I removed the sunglasses class entirely and replaced it with coins. This allowed me to maintain the same camera angle and similar hand coverage while keeping subject size consistent.

    After swapping the class and standardizing the framing, the model performed much better. Interestingly, when the frame was blank (no object present), the model consistently predicted "coins" with 100% confidence—suggesting the model is designed to always output a class. It might be helpful to test this by training with an explicit "empty" or "background" class.

2. Challenges & Observations

    The model performed best with watches, likely because they were the largest objects and had a wide range of colors and reflective surfaces depending on the angle.

    Batteries were also well-classified, probably due to their consistent cylindrical shape and limited surface variation.

    The sunglasses class was the most problematic. The challenge was keeping the large object in-frame without hands covering significant portions of it. If I had more time, I would’ve used fishing line or a suspension rig to isolate the object from my hands.

    I noticed that curved objects (like a nasal spray bottle) were often misclassified as batteries, but when rotated to a flat view, they were instead classified as watches with 100% confidence.

3. Bias in AI

    I used three distinct examples for each class, and the model performed reasonably well when I introduced new but similar objects. For example, it handled other watches not in the training set effectively.

    That said, I suspect it would misclassify a coin-shaped battery (like a CR2032) as a coin due to shape similarity—though I didn’t have one on hand to test.

    I also tested a flashlight, and the model leaned toward classifying it as a battery. Notably, all environmental variables (lighting, camera angle, background) were kept constant—tripod-mounted camera, black surface, consistent lighting—so the result seems rooted in visual similarity bias.

4. Model Limitations & Usefulness

    Focal length was a major limitation. After training, I moved the camera slightly back, and suddenly the model failed to recognize coins—even when they were the only object in the frame. Watches still performed okay, but battery detection dropped significantly.

    With more time and a larger, more diverse training set, these models could be exported and shared to help others detect similar objects. They could also be fine-tuned by experts and re-imported for improvement in my own application.

5. Real-World Applications & Ethics

    One real-world use case could be inserting a camera array into a refrigerator to monitor inventory levels. As items are used, the system could auto-generate a grocery list or pre-fill a shopping cart at your favorite store. It could also suggest recipes based on what you have or alert you when you're missing ingredients before you start cooking. (I've personally run into that problem!)

    A major ethical concern I experienced firsthand during this project was privacy. While streaming video to Teachable Machine, it’s unclear how Google handles or stores that webcam data. Even though I wasn’t doing anything sensitive, I still found myself wondering, who else could be watching or listening? And what about the microphone?

(Optional) Challenges Faced / Interesting Discoveries

    Moving the webcam was unexpectedly difficult due to tight desk cable management. I barely had enough slack to get it mounted on a tripod, facing downward. The setup was a bit of a battle.

(Optional) Screenshot![Screenshot at 2025-06-19 15-43-48](https://github.com/user-attachments/assets/a1a4bba1-a696-4775-9271-015355b93492)


