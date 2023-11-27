# EVC-Finder-assignment
The provided code includes a basic structure for a React Native application for an online store, integrated with Redux for state management. The application is designed to allow users to register, login, view products, add new products, view product details, and navigate through category-wise product lists.
// LoginScreen.js
import React from 'react';
import { View, Text } from 'react-native';

const LoginScreen = () => {
  return (
    <View>
      <Text>Login Screen</Text>
    </View>
  );
};

export default LoginScreen;

// RegisterScreen.js
import React from 'react';
import { View, Text } from 'react-native';

const RegisterScreen = () => {
  return (
    <View>
      <Text>Register Screen</Text>
    </View>
  );
};

export default RegisterScreen;

// HomeScreen.js
import React from 'react';
import { View, Text } from 'react-native';

const HomeScreen = () => {
  return (
    <View>
      <Text>Home Screen</Text>
    </View>
  );
};

export default HomeScreen;

// ProductDetailScreen.js
import React from 'react';
import { View, Text } from 'react-native';

const ProductDetailScreen = () => {
  return (
    <View>
      <Text>Product Detail Screen</Text>
    </View>
  );
};

export default ProductDetailScreen;

// AddProductScreen.js
import React from 'react';
import { View, Text } from 'react-native';

const AddProductScreen = () => {
  return (
    <View>
      <Text>Add Product Screen</Text>
    </View>
  );
};

export default AddProductScreen;

// CategoryScreen.js
import React from 'react';
import { View, Text } from 'react-native';

const CategoryScreen = () => {
  return (
    <View>
      <Text>Category Screen</Text>
    </View>
  );
};

export default CategoryScreen;

// App.js
import React from 'react';
import { NavigationContainer } from '@react-navigation/native';
import { createDrawerNavigator } from '@react-navigation/drawer';
import { createStackNavigator } from '@react-navigation/stack';
import { Provider } from 'react-redux';
import store from './redux/store'; // Assuming you have set up Redux store

import LoginScreen from './screens/LoginScreen';
import RegisterScreen from './screens/RegisterScreen';
import HomeScreen from './screens/HomeScreen';
import ProductDetailScreen from './screens/ProductDetailScreen';
import AddProductScreen from './screens/AddProductScreen';
import CategoryScreen from './screens/CategoryScreen';

const Drawer = createDrawerNavigator();
const Stack = createStackNavigator();

const AuthStack = () => {
  return (
    <Stack.Navigator>
      <Stack.Screen name="Login" component={LoginScreen} />
      <Stack.Screen name="Register" component={RegisterScreen} />
    </Stack.Navigator>
  );
};

const AppStack = () => {
  return (
    <Drawer.Navigator>
      <Drawer.Screen name="Home" component={HomeScreen} />
      <Drawer.Screen name="Category" component={CategoryScreen} />
    </Drawer.Navigator>
  );
};

const App = () => {
  return (
    <Provider store={store}>
      <NavigationContainer>
        <Stack.Navigator>
          <Stack.Screen name="Auth" component={AuthStack} />
          <Stack.Screen name="App" component={AppStack} />
          <Stack.Screen name="AddProduct" component={AddProductScreen} />
          <Stack.Screen name="ProductDetail" component={ProductDetailScreen} />
        </Stack.Navigator>
      </NavigationContainer>
    </Provider>
  );
};

export default App;

