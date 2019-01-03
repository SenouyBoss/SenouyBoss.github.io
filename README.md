# SenouyBoss.github.io
first commit

import React from 'react';
import {StyleSheet, View, Text, TextInput, Button} from 'react-native';



export default class App extends React.Component{
	constructor(){
    super();
		this.state = {
			word: "",
			vowel: 0,
			encry: '',
			numbers: 0,
			nword: "",

		};
	}


	analyze(){
		this.state.word.toLowerCase();
    var word_arr = this.state.word.split('');
	var v=0, c=0, n=0;
	//this.setState({nword: word_arr});
	n = word_arr.length;
	console.log(n); // just a test function for me to see if split is working
	this.setState({numbers: word_arr.length});
		for(i=0; i< word_arr.length; i++){
			if( word_arr[i]== 'a' || 
				word_arr[i]== 'o' ||
				word_arr[i]== 'u' ||
				word_arr[i]== 'i' ||
				word_arr[i]== 'e' 
			){
        word_arr[i] = '$';
			}
			
			
      
    }	
  
  word_arr.join('');
    this.setState({vowel: v});
     // this.setState({numbers: n});
      this.setState({nword: word_arr});	
  }


	render(){
		return (
			<View style={styles.container}>

				<View style={styles.header}>
				<Text style={{color: 'purple', fontSize: 20, fontWeight: 'bold'}}> A Word Encryptor </Text>
				</View>

				<View style={styles.content}>

				<Text style={{color: 'red', fontSize: 15, fontWeight: 'bold'}}> Word  {"\n"}</Text>
				<TextInput placeholder="Your word" onChangeText={(word)=> this.setState({word})} />
				<Text> {"\n"}  </Text>
				<Button   title='Encrypt' onPress={()=> {this.analyze();}} />
				<Text> {"\n"}  </Text>
				<Text> word: {"\t"}{"\t"}{"\t"}{"\t"}{"\t"}{"\t"} {this.state.word} </Text> 
				<Text> Encypt: {"\t"}{"\t"} {this.state.nword} </Text> 
				 
				<Text> number: {"\t"}{"\t"}{"\t"}{"\t"} {this.state.numbers} </Text> 
				</View>

				<View style={styles.footer}>
				</View>

			</View>
		)
  }
}

	const styles = StyleSheet.create({
		container:{
			flex:1,
			alignItems: 'center',
    	justifyContent: 'center',
		},
		header: {
			flex: 1,
			alignItems: 'center',
			justifyContent: 'center',
			
			
		},

		content: {
			flex: 1,
			justifyContent: 'center',
			alignItems: 'stretch',
		},

		footer: {
			flex:1,
		},
	});
