pipeline {
    agent any
    
    stages {
        stage('Clone Repository') {
            steps {
                // Clone the repository using credentialsId
                git branch: 'master', credentialsId: 'your-credentials-id', url: 'https://github.com/Aditya-jaiswal07972/Project.git'
            }
        }
        
        stage('Build and Run Python Script') {
            steps {
                // Navigate to the directory containing your Python script
                dir('path/to/your/python/script') {
                    // Install any required dependencies using pip
                    bat 'pip install -r requirements.txt'
                    
                    // Generate the captcha image and run the Python script
                    bat 'python python-captcha.py'
                    
                    // Optionally, capture the output of the script and save it to a file
                    // bat 'python python-captcha.py > output.txt'
                }
            }
        }
    }
}
