Git is a powerful centralized version control system (VCS) and collaboration tool widely employed by both system admins and devs in the DevOps ecosystem. It plays a crucial role in maintaining and managing multiple versions of applications, source code, documentation, and other project files.

ref: 
https://www.udemy.com/course/decodingdevops/


https://medium.com/@samsamarullah/basic-git-github-for-devops-engineers-38c8a789909e


GPT 😁

Key Functions:

Version Tracking and Management:

Git enables meticulous tracking and management of different versions of project elements. This is instrumental in understanding the evolution of code, identifying changes, and attributing modifications to specific contributors.

Rollback Capability:

With Git, the ability to rollback to any previous version becomes a cornerstone feature. This is especially crucial in DevOps workflows, allowing teams to revert changes in case of issues or unexpected behavior.

Branching and Merging:

DevOps engineers leverage Git's robust branching and merging capabilities. This allows for the creation of isolated branches for new features or bug fixes, which can later be merged back into the main codebase, promoting a structured and organized development workflow.

Collaborative Development:

Git facilitates seamless collaboration among distributed teams. Developers can work concurrently on the same project, and Git intelligently merges changes, preventing conflicts and ensuring a smooth collaborative development process.

Integration with CI/CD:

Git integrates seamlessly with Continuous Integration (CI) and Continuous Deployment (CD) pipelines. DevOps engineers utilize Git hooks and webhooks to trigger automated processes, ensuring that changes are validated, built, and deployed consistently.

Infrastructure as Code (IaC):

In a DevOps landscape, Git is often utilized for versioning Infrastructure as Code (IaC) scripts and configurations. This ensures that changes to infrastructure are tracked, reproducible, and can be rolled back if needed.

Code Reviews:

Git platforms commonly support code review processes, allowing DevOps teams to conduct thorough reviews of changes before merging them into the main codebase. This contributes to maintaining code quality and adherence to best practices.

Auditing and Compliance:

Git logs and commit histories provide an audit trail, which is valuable for compliance purposes. DevOps engineers can trace the evolution of the system and document changes for regulatory requirements.

Distributed and centralized Configuration:

Configuring Git as a centralized version control system involves establishing a central repository (server) and allowing clients (developers or systems) to interact with it. This centralized approach ensures a single source of truth for the project's version history.

In summary, Git's versatility and capabilities make it an powerful tool in DevOps providing a solid foundation for version control, collaboration, and automation in software development and system administration workflows.

***************************************************************************

Launch and Amazon Linux ec2

yum install git

git --version

git version 2.43.0

Create an SSH Pub key to configure it with your GitHub account

ssh-keygen -t rsa -b 4096 -C "elsonpulikkan@gmail.com"

eval "$(ssh-agent -s)" && ssh-add ~/.ssh/id_rsa

cat ~/.ssh/id_rsa.pub

ssh-rsa AAA**************************************gr4CW2n91qAXIW7a08NIycZ1T/QllHleCpZ2svWxxSGIfZrBM0YuckJBmzuNf/EN9wNRfnqyNbmOYkDAb7QTuT+8X/6/66PcnqWQrTxDDK2McNVngd3gQknmZ0dIDxoXZoWwwnLSR3GCMzf6wMiRI/7aWEqbEFAOvR5LVlcf5XjJRliv/BtRTTo+/Y00yKft5E0Rldi+72S87ht2K2ERtXp0zIrYe+Ins1xhIdCJ7PfkdAQQfOvBcjQp05fPlBYkQ3P75SZh0mUkXsOsr929l5n9syfoJGEazkGzo33nF9ywOAdNmg /+s5OnnSRf61LjHrBr42hx4w== xxxx@gmail.com

<<< Copy and paste the SSH pub key value to the GitHub account, Follow the below steps >>> 

Open your GitHub account >  settings.
Go to "SSH and GPG keys."
Click "New SSH key."

Paste the copied key into the "Key" field and add

Check connection: ssh -T git@github.com

Follow the below steps to configure your Git identity on the server and set your username and email. Afterwards, login to your GitHub account create an empty public or private repository and track its URL

eg: https://github.com/elsonpulikkan96/git-basics

Afterwards, clone this repository you created on your GitHub account to your local machine.


git clone https://github.com/elsonpulikkan96/git-basics

set the remote URL of the Repo to Use SSH


git remote add origin git@github.com:elsonpulikkan96/git-basics


git remote set-url origin git@github.com:elsonpulikkan96/git-basics


Run the following command to see the current remote URL:

git remote -v

Now the Repo will be already downloaded on your local machine, Go to the cloned remote repo, create a HelloWorld python file andpush the file to the main branch of the Repo.

cd git-basics

Set Git identity on the server, set your username and email

git config --global user.name "elson"
git config --global user.email "elsonpulikkan@gmail.com"

git init -  command is used to initialize the Git repository on locally

touch helloworld.py

echo 'print("Hello, World!")' > helloworld.py

git status - To check the status

git ls-files - To list the files in the current working directory

git add helloworld.py - To add the file as object to Git index

git commit -m "Explain Git Workflow with a Python welcome page for nginx"

git push -u origin main

