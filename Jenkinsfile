pipeline {
    agent any
    
    stages {
        stage('Clone Repository') {
            steps {
                // Clone the repository containing your Python script
                git branch: 'main', credentialsId: 'jenkin1', url: 'https://github.com/Aditya-jaiswal07972/Project.git'
            }
        }
        
        stage('Build and Run Python Script') {
            steps {
                // Navigate to the directory containing your Python script
                dir('blob/main/python-captha.py') {
                    // Install any required dependencies using pip
                    sh 'pip install -r requirements.txt'
                    
                    // Generate the captcha image and run the Python script
                    sh 'python python-captcha.py'
                    
                    // Optionally, capture the output of the script and save it to a file
                    // sh 'python python-captcha.py > output.txt'
                }
            }
        }
    }
}
