<template>
  <div class="about">
    <Header />
    <div class="container">
      <p>To do lists don't need to be complicated—plenty of people use a pen and paper for the job without any problem. And yet a new to do list app seems to come out every day. Why? Because keeping track of your tasks is an intensely personal thing, and people will reject anything that doesn't feel right pretty much instantly. That makes it hard to find the right app.</p>
      <h4>What Makes a Great To Do List App?</h4>
      <p>When it comes to do lists everyone has different criteria. We kept this in mind as we tested applications and noticed a few features that made apps stand out. The best to do list apps:</p>
      <ul>
        <li><strong>Make it fast to add and organize tasks.</strong> Ideally a task is added and categorized in a couple taps or keystrokes.</li>
        <li><strong>Offer multiple ways to organize your tasks.</strong> Tags, lists, projects, and due dates are all helpful, and the best apps offer at least a few categories like this.</li>
        <li><strong>Remind you about self-imposed deadlines.</strong> Notifications, widgets, emails—the best applications make it obvious when something needs to be completed.</li>
        <li><strong>Offer clean user interfaces.</strong> Well-designed to do apps fit into your workflow so you can get back to what you're supposed to be doing.</li>
        <li><strong>Sync between every platform you use.</strong> Which platforms is going to depend on what you personally use, but we didn't consider anything that doesn't sync between desktop and mobile.</li>
      </ul>
      <p>We tried to find the best applications that balance these things in various ways. None of these apps will be right for everyone, but hopefully one of them is right for you. Let's dive in.</p>
    </div>
  </div>
</template>

<script>
import Header from "../components/layout/Header"
export default {
  components: {
    Header
  }
}
</script>

<style scoped>
  p {
    margin-top: 10px;
  }
</style>