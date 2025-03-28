- 👋 Hi, I’m @Gaugau00
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...

<!---
Gaugau00/Gaugau00 is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
import React, { useState } from 'react';
import { View, Text, Button, StyleSheet } from 'react-native';
import ThemeContextProvider from './context/ThemeContext';
import Conversations from './components/Conversations';
import Tasks from './components/Tasks';

const App = () => {
  const [currentTab, setCurrentTab] = useState('Conversations');

  return (
    <ThemeContextProvider>
      <View style={styles.container}>
        {currentTab === 'Conversations' ? (
          <Conversations />
        ) : (
          <Tasks />
        )}
        <View style={styles.tabBar}>
          <Button title="Conversations" onPress={() => setCurrentTab('Conversations')} />
          <Button title="Tasks" onPress={() => setCurrentTab('Tasks')} />
        </View>
      </View>
    </ThemeContextProvider>
  );
};

const styles = StyleSheet.create({
  container: {
    flex: 1,
    backgroundColor: '#121212',
  },
  tabBar: {
    flexDirection: 'row',
    justifyContent: 'space-around',
    padding: 10,
    backgroundColor: '#1e1e1e',
  },
});

export default App;
