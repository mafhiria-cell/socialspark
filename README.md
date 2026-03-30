youtube link:https://youtu.be/Z8JkhHn69Pw?si=Kkau4apGDTj0Sfto
1)what is it about ?
My close friend Corah has been struggling with maintaining social connections during busy days. Cora is hoping to simplify social interactions based on the time of the day,they need an easy to use Android app that suggests small social “sparks” or actions based on whether it is morning,afternoon or evening.

2)Social Spark Suggestion logic
- Morning: ”Send a ‘good morning’ text to A family member.
-  Mid-morning : “ Reach out to a colleague with a quick “thank you.”
- Afternoon: Share a funny meme or interesting link with a friend.
- Afternoon Snack time: “Send a  quick ‘thinking of you’ message.
- Dinner: Call a friend or relative for a 5-minute catch up.
-After Dinner/Night: leave a thoughtful comment on a friend’s post

3)Error Handling 
-Ensures that the app handles input errors,providing constructive feedback if they enter invalid information.
4)Testing and automated testing
- Conduct manual testing to ensure the app functions seamless and make use logs to assist here.No uni test are needed
-Make use of Github Actions to run tests and build your code to make sure it will work not just on your computer.
class MainActivity : AppCompatActivity() {
// declarig
    lateinit var txtinput: EditText
    lateinit var txtResult: TextView
    lateinit var btnsubmit: Button
    lateinit var btnClear : Button


    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        enableEdgeToEdge()
        setContentView(R.layout.activity_main)
//mapping
        txtinput = findViewById(R.id.txtInput)
        txtResult = findViewById(R.id.txtResult)
        btnsubmit = findViewById(R.id.btnSubmit)
        btnClear = findViewById(R.id.btnClear)

//all present fields
        btnsubmit.setOnClickListener {
            val timeofday =
                txtResult.text.toString().lowercase()
            if (timeofday == "morning") {
                txtResult.text = ("Send a 'good morning' text to a family member.")
            } else if (timeofday == "mid morning") {
                txtResult.text = ("Reach out to a collegue with a quick 'Thank you'.")
            } else if (timeofday == "afternoon") {
                txtResult.text = ("Share a funny meme or intresting link with a friend.")
            } else if (timeofday == "afternoon snack") {
                txtResult.text = ("Send a quick 'Thinking of you' message.")
            } else if (timeofday == "dinner"){
                txtResult.text = ("Call a freind or relative for 5minutes to catch up.")
            }else if (timeofday == "night"){
                txtResult.text = ("leave a thoughtful comment of a freinds post")
            }else {
                txtResult.text = ("invalid time of day. Try: Morning,Afternoon,Dinner")
            }
        }
        btnClear.setOnClickListener {
            txtinput.text.clear()
            txtResult.setText("")
        }
