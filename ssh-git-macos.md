# Setting Up a New SSH Key with a Custom Name

## 1. Generate a New SSH Key with a Custom Name
ssh-keygen -t ed25519 -C "your_email@example.com" -f ~/.ssh/my_new_key

## 2. Add the New Key to the SSH Agent
eval "$(ssh-agent -s)"
ssh-add --apple-use-keychain ~/.ssh/my_new_key
ssh-add ~/.ssh/my_new_key

## 3. Copy the New Key to Clipboard (for GitHub/GitLab)
pbcopy < ~/.ssh/my_new_key.pub
echo "Public key copied to clipboard. Add it to your GitHub/GitLab SSH settings."

## 4. Configure SSH for the New Key
nano ~/.ssh/config

Host github.com-mynewkey
    HostName github.com
    User git
    IdentityFile ~/.ssh/my_new_key

## 5. Test the New Key
ssh -T git@github.com-mynewkey