# html-code-to-convert-audio-to-text
<!doctype html>
	<head>
		<style>
			/* CSS */
			body {
                padding:80px;
                background-color: rgba(255, 255, 255, 0.449);
                text-align: center;
                color: black;
			    font-family:Georgia, 'Times New Roman', Times, serif;
                font-size: large;
			}
			button {
			    padding:10px;
			    background-color: #8d5786d4;
			    cursor:pointer;
                margin-top:30px;
			}
			#output {
			    background-color:#8d57862f;
			    padding:15%;
			    width: 25px 50px 25px 75px;
			    margin-top:50px;
			    line-height:30px;
			}
			
		</style>
		<title>Convert Audio to Text</title>
	</head>
	<body>
		<h2>Convert Audio to Text</h2>
        <p><button type="button" onclick="runSpeechRecognition()">Start</button> &nbsp; <span id="action"></span></p>
        <div id="output" ></div>
		<script>
			/* JS */
		    function runSpeechRecognition() {
		        var action = document.getElementById("action");
				var output = document.getElementById("output");
               
                // new speech recognition object
                var SpeechRecognition = SpeechRecognition || webkitSpeechRecognition;
                var recognition = new SpeechRecognition();
            
                // runs 
                recognition.onstart = function() {
                    action.innerHTML = "<small>listening, please speak...</small>";
                };

                recognition.onresult = function(event) {
                    var transcript = event.results[0][0].transcript;
                    output.innerHTML = transcript ;
                };
              
                 // start recognition
                 recognition.start();
	        }
		</script>
	</body>
</html>
