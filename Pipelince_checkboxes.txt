pipeline {
    agent any
    
    parameters{
        
        extendedChoice(
            name: 'TestCases',
            type: 'PT_CHECKBOX',
            value: 'TEST1, Test2, Test3, Test4, Test5, Test6',
            defaultValue: 'Test2, Test3',
            description: 'Please select Tests you want to run',
            visibleItemCount: 5,
            multiSelectDelimiter: ',',
            quoteValue: true,
            
        )
    }

    stages {
        stage('testing') {
            steps {
                echo "Tests will run ----${params.TestCases}"
            }
        }
    }
}
