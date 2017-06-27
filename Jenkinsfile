def flow

// 使用node01节点进行接下来的脚本执行
node("master"){
    stage('Preparation') {
      echo 'The Preparation stage get code from SCM'
    }

    stage('Compile') {
      echo 'The Compile stage'
    }

    stage('Unit Test') {
      echo 'The Unit Test stage'
    }

    stage('Code Analysis') {
      echo 'The Code Analysis stage'
    }

    stage('Build') {
      echo 'The Build stage'
    }

    stage('Deploy Dev Stage') {
      echo 'The Build stage'
    }

    stage('Smoke Test') {
      echo 'The Smoke Test stage'
    }

    // 测试环境
    stage name: 'Deploy Test Stage', concurrency: 1

    // 添加手工干预步骤
    timeout(time:1, unit:"DAYS")
    {
        input message: "Everythingd build successfully?"
    }

    stage('Regression Test') {
      echo 'The Regression Test stage'
    }

    // 生产环境
    stage name: 'Production Stage', concurrency: 1

    // 添加手工干预步骤
    timeout(time:1, unit:"DAYS")
    {
        input message: "Did all tests pass?"
    }

    stage('Store Artifact') {
      echo 'The Store Artifact stage'
    }
}
